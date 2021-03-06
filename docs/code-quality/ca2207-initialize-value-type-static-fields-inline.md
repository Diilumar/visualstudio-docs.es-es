---
title: 'CA2207: Inicializar campos estáticos de tipo de valor insertados'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b00403af731439ecef4667c632e53b52670afff
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926884"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicializar campos estáticos de tipo de valor insertados

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|Identificador de comprobación|CA2207|
|Categoría|Microsoft.Usage|
|Cambio problemático|No trascendental|

## <a name="cause"></a>Motivo
 Un tipo de valor declara un constructor estático explícito.

## <a name="rule-description"></a>Descripción de la regla
 Cuando se declara un tipo de valor, se somete a una inicialización predeterminada donde todos los campos de tipo de valor se establecen en cero y todos los campos de tipo de referencia se establecen en `null` (`Nothing` en Visual Basic). Un constructor estático explícito solo se garantiza para ejecutar antes de un constructor de instancia o se llama al miembro estático del tipo. Por lo tanto, si el tipo se crea sin una llamada a un constructor de instancia, el constructor estático no se garantiza para ejecutar.

 Si todos los datos estáticos está alineada inicializado y no se declara ningún constructor estático explícito, los compiladores de C# y Visual Basic agregan el `beforefieldinit` marca a la definición de clase MSIL. También, los compiladores agregan un constructor estático privado que contiene el código de inicialización estática. Este constructor estático privado se garantiza que se ejecutará antes de que se tiene acceso a los campos estáticos del tipo.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla inicializar todos los datos estáticos cuando se declara y quite el constructor estático.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias
 No suprima las advertencias de esta regla.

## <a name="related-rules"></a>Reglas relacionadas
 [CA1810: Inicializar campos estáticos de tipo de referencia insertados](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)