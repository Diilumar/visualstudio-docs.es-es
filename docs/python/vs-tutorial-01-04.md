---
title: Trabajar con Python en Visual Studio, paso 4 | Microsoft Docs
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 90f22c2f7626b09f230c497c54c8a37511ea1b0b
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-4-running-code-in-the-debugger"></a>Paso 4: Ejecución de código en el depurador

**Paso anterior: [Uso de la ventana interactiva de REPL](vs-tutorial-01-03.md)**

Además de administrar proyectos, ofrecer una experiencia de edición enriquecida y la ventana interactiva, Visual Studio proporciona una depuración completa para el código Python. En el depurador, puede ejecutar el código paso a paso, incluida cada una de las iteraciones de un bucle. También puede pausar el programa cuando ciertas condiciones sean verdaderas. En cualquier momento en el que el programa esté pausado en el depurador, puede examinar el estado del programa completo y cambiar el valor de las variables. Estas acciones son esenciales para el seguimiento de los errores de programa y también proporcionan una ayuda muy útil para seguir con cuidado el flujo del programa exacto.

1. Reemplace el código del archivo `PythonApplication1.py` por lo siguiente. Esta variación del código expande `make_dot_string` para que pueda examinar sus pasos discretos en el depurador. También coloca el bucle `for` en una función `main` y lo ejecuta explícitamente mediante una llamada a esa función:

    ```python  
    import sys  
    from math import sin, cos, radians    
    
    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        rad = radians(x)                             # cos works with radians
        numspaces = int(20 * cos(radians(x)) + 20)   # scale to 0-40 spaces
        str = ' ' * numspaces + 'o'                  # place 'o' after the spaces
        return str
    
    def main():  
        for i in range(0, 1800, 12):
            s = make_dot_string(i)  
            print(s)  
            
    main()
    ```  

1. Compruebe que el código funciona correctamente presionando F5 o seleccionando el comando de menú **Depurar > Iniciar depuración**. Este comando ejecuta el código en el depurador, pero dado que aún no ha hecho nada para pausar el programa mientras se está ejecutando, solo imprime un patrón ondulado para algunas iteraciones. Al presionar una tecla, se mostrará la ventana de salida.

    > [!Tip]
    > Para cerrar la ventana de salida automáticamente cuando se completa el programa, reemplace la llamada `main()` con el código siguiente:
    >
    > ```python    
    > if __name__ == "__main__":  
    >     sys.exit(int(main() or 0))      
    > ```    

1. Establezca un punto de interrupción en la instrucción `for` haciendo clic una vez en el margen gris junto a esa línea o colocando el operador exponencial en dicha línea y usando el comando **Depurar > Alternar puntos de interrupción** (F9). Aparecerá un punto rojo en el margen gris para indicar el punto de interrupción (como indica la flecha a continuación):

    ![Establecer un punto de interrupción](media/vs-getting-started-python-18-debugging1.png)

1. Vuelva a iniciar el depurador (F5) y verá que, al ejecutar el código, se detiene en la línea en que se ha establecido el punto de interrupción. Aquí puede inspeccionar la pila de llamadas y examinar variables. Las variables que están en dentro del ámbito aparecen en la ventana **Automático** cuando están definidas; también puede cambiar a la vista **Variables locales**, situada en la parte inferior de esa ventana, para mostrar todas las variables que Visual Studio encuentre en el ámbito actual (influidas funciones), incluso antes de que se definan:

    ![Experiencia de interfaz de usuario de puntos de interrupción para Python](media/vs-getting-started-python-19-debugging2b.png)

1. Observe la barra de herramientas de depuración (que se muestra a continuación) a lo largo de la parte superior de la ventana de Visual Studio. Esta barra de herramientas proporciona acceso rápido a los comandos de depuración más comunes (que también se pueden encontrar en el menú **Depurar**):

    ![Botones esenciales de la barra de herramientas de depuración](media/vs-getting-started-python-20-debugging3.png)

    Los botones son los siguientes de izquierda a derecha:
    - **Continuar** (F5) ejecuta el programa hasta el siguiente punto de interrupción o hasta la finalización del programa.
    - **Interrumpir todo** (Ctrl + Alt + Inter) pone en pausa un programa de ejecución prolongada.
    - **Detener depuración** (Mayús + F5) detiene el programa dondequiera que esté y sale del depurador.
    - **Reiniciar** (Ctrl + Mayús + F5) detiene el programa dondequiera que esté y lo reinicia desde el principio en el depurador.
    - **Mostrar la instrucción siguiente** (Alt + núm *) cambia a la siguiente línea de código que se debe ejecutar. Esto resulta especialmente útil si al navegar por el código durante una sesión de depuración desea volver rápidamente al punto donde se pausó el depurador.
    - **Paso a paso por instrucciones** (F11) ejecuta la siguiente línea de código, entrando en las funciones llamadas.
    - **Paso a paso por procedimientos** (F10) ejecuta la siguiente línea de código sin entrar en las funciones llamadas.
    - **Paso a paso para salir** (Mayús + F11) ejecuta el resto de la función actual y se pausa en el código de llamada.

1. Depure paso a paso por procedimientos la instrucción `for` mediante **Paso a paso por procedimientos**. La ejecución *paso a paso* significa que el depurador ejecuta la línea de código actual, incluidas las llamadas de función y luego se pone en pausa otra vez inmediatamente. Observe cómo la variable `i` ahora está definida en las ventanas **Variables locales** y **Automático**.
 
1. Depure paso a paso por procedimientos la siguiente línea de código, que llama a `make_dot_string` y se pone en pausa. Depurar paso a paso significa aquí que el depurador ejecuta toda la función `make_dot_string` y se pone en pausa cuando se devuelve. El depurador no se detiene dentro de esa función a menos que exista un punto de interrupción independiente.

1. Continúe ejecutando paso a paso por procedimientos el código varias veces y observe cómo cambian los valores de las ventanas **Variables locales** o **Automático**.

1. En la ventana **Variables locales** o **Automático**, haga doble clic en la columna **Valor** para las variables `i` o `s` a fin de editar el valor. Presione Entrar o haga clic fuera de ese valor para aplicar los cambios.

1. Continúe ejecutando paso a paso el código usando **Paso a paso por instrucciones**. Depurar paso a paso por instrucciones significa que el depurador entra dentro de cualquier llamada de función para la que tenga información de depuración, como `make_dot_string`. Una vez dentro de `make_dot_string` puede examinar sus variables locales y recorrer su código en concreto.
 
1. Continúe con la ejecución paso a paso por instrucciones y tenga en cuenta que, cuando llegue al final de la función `make_dot_string`, el paso siguiente vuelve al bucle `for` con el nuevo valor devuelto en la variable `s`. Mientras ejecuta de nuevo la instrucción `print`, observe que Paso a paso por instrucciones en `print` no entra en esa función. Esto se debe a que `print` no está escrita en Python, sino que es código nativo dentro del tiempo de ejecución de Python.

1. Continúe usando Paso a paso por instrucciones hasta que esté de nuevo en la mitad de `make_dot_string`. Luego, use **Paso a paso para salir** y observe que vuelve al bucle `for`. Con Paso a paso para salir, el depurador ejecuta el resto de la función y, luego, se pausa automáticamente en el código de llamada. Esto resulta muy útil cuando ha recorrido una parte de una función larga que desea depurar, pero no necesita recorrer el resto y no desea establecer un punto de interrupción explícito en el código de llamada.

1. Para continuar ejecutando el programa hasta que se alcance el siguiente punto de interrupción, use **Continuar** (F5). Puesto que hay un punto de interrupción en el bucle `for`, la interrupción se producirá en la siguiente iteración.

1. Recorrer cientos de iteraciones de un bucle puede resultar tedioso, por lo que Visual Studio le permite agregar una *condición* a un punto de interrupción. De esta forma, el depurador pausa el programa en el punto de interrupción solo cuando se cumple la condición. Por ejemplo, puede usar una condición con el punto de interrupción en la instrucción `for` de modo que solo se ponga en pausa cuando el valor de `i` sea superior a 1600. Para establecer una condición, haga clic con el botón derecho en el punto rojo del punto de interrupción y seleccione **Condiciones...** (Alt + F9, C). En el elemento emergente **Configuración del punto de interrupción** que aparece, escriba `i > 1600` como expresión y seleccione **Cerrar**. Presione F5 para continuar y observe que el programa ejecuta muchas iteraciones antes de la interrupción siguiente. 

    ![Definición de una condición de punto de interrupción](media/vs-getting-started-python-21-debugging4.png)

1. Para ejecutar el programa hasta su finalización, deshabilite el punto de interrupción haciendo clic con el botón derecho y seleccionando **Deshabilitar punto de interrupción** (Ctrl + F9). Luego, seleccione **Continuar** (o presione F5) para ejecutar el programa. Cuando se finalice el programa, Visual Studio detiene la sesión de depuración y vuelve a su modo de edición. Tenga en cuenta que también puede eliminar el punto de interrupción haciendo clic en su punto, pero esto también elimina cualquier condición que haya establecido.

> [!Tip]    
> En algunas situaciones, como un error al iniciar el intérprete de Python, la ventana de salida puede aparecer solo brevemente y luego cerrarse de forma automática sin darle la oportunidad de ver los mensajes de error. Si esto ocurre, haga clic con el botón derecho en el proyecto en el Explorador de soluciones, seleccione **Propiedades**, la ficha **Depurar** y, después, agregue `-i` al campo **Argumentos del intérprete**. Este argumento hace que el intérprete entre en modo interactivo una vez que se haya finalizado un programa, con lo que la ventana se mantendrá abierta hasta que pulse Ctrl + Z, Entrar para salir.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Installing packages in your Python environment (Instalación de paquetes en su entorno de Python)](vs-tutorial-01-05.md)

### <a name="going-deeper"></a>Mayor profundización
- [Debugging](debugging.md) (Depuración).
- [Debugging in Visual Studio (Depurar en Visual Studio)](../debugger/debugging-in-visual-studio.md) ofrece documentación completa sobre las características de depuración de Visual Studio.