---
title: 'Gewusst wie: Implementieren von Rückruffunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
ms.openlocfilehash: b7aae1e70ac736d60bed1e79291235db1c220281
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181418"
---
# <a name="how-to-implement-callback-functions"></a>Gewusst wie: Implementieren von Rückruffunktionen
Im folgenden Verfahren und Beispiel wird veranschaulicht, wie eine verwaltete Anwendung den Handlewert für jedes Fenster auf dem lokalen Computer mithilfe eines Plattformaufrufs drucken kann. Insbesondere verwenden das Verfahren und das Beispiel die **EnumWindows**-Funktion, um die Liste von Fenstern und eine verwaltete Rückruffunktion (namens „CallBack“) zu durchlaufen, um den Wert des Fensterhandles auszugeben.  
  
### <a name="to-implement-a-callback-function"></a>So implementieren Sie die Rückruffunktion  
  
1. Betrachten Sie die Signatur für die **EnumWindows**-Funktion, bevor Sie mit der Implementierung fortfahren. **EnumWindows** weist die folgende Signatur auf:  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     Ein Hinweis darauf, dass diese Funktion einen Rückruf erfordert, ist das Vorkommen des **lpEnumFunc**-Arguments. Es ist üblich, das Präfix **lp** (Long-Zeiger) zusammen mit dem Suffix **Func** im Namen von Argumenten zu sehen, die einen Zeiger auf eine Rückruffunktion verwenden. Eine Dokumentation zu den Win32-Funktionen finden Sie im Microsoft Platform SDK.  
  
2. Erstellen Sie die verwaltete Rückruffunktion. Im Beispiel wird ein Delegattyp namens `CallBack` deklariert, der zwei Argumente übernimmt (**hwnd** und **lparam**). Das erste Argument ist ein Handle für das Fenster. Das zweite Argument wird von der Anwendung definiert. In diesem Release müssen beide Argumente ganze Zahlen sein.  
  
     Rückruffunktionen geben im Allgemeinen bei einer erfolgreichen Ausführung einen Wert ungleich Null zurück, während ein Fehler durch 0 (null) angezeigt wird. In diesem Beispiel wird der Rückgabewert explizit auf **TRUE** festgelegt, um die Enumeration fortzusetzen.  
  
3. Erstellen Sie einen Delegaten, und übergeben Sie ihn als Argument an die **EnumWindows**-Funktion. Ein Plattformaufruf konvertiert den Delegaten automatisch in ein vertrautes Rückrufformat.  
  
4. Stellen Sie sicher, dass der Garbage Collector den Delegaten nicht freigibt, bevor die Rückruffunktion ihre Arbeit abgeschlossen hat. Wenn Sie einen Delegaten als Parameter oder als in einer Struktur enthaltenes Feld übergeben, wird er für die Dauer des Aufrufs nicht erfasst. Ebenso ist dies der Fall im folgenden Enumerationsbeispiel, in dem die Rückruffunktion ihre Arbeit beendet, bevor der Aufruf zurückkehrt. Daher erfordert sie keine zusätzliche Aktion des verwalteten Aufrufers.  
  
     Wenn die Rückruffunktion jedoch nach der Rückkehr des Aufrufs aufgerufen werden kann, muss der verwaltete Aufrufer Maßnahmen ergreifen, um sicherzustellen, dass der Delegat weiterhin nicht erfasst wird, bevor die Rückruffunktion abgeschlossen ist. Ausführliche Informationen zum Verhindern der Garbage Collection finden Sie unter [Interop-Marshalling](interop-marshaling.md) mit Plattformaufruf.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);
  
    public static void Main()
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Rückruffunktionen](callback-functions.md)
- [Aufrufen einer DLL-Funktion](calling-a-dll-function.md)
