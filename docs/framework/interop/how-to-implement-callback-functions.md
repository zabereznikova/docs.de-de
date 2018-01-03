---
title: "Gewusst wie: Implementieren von Rückruffunktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819861f9bf13f9af3fab7a1ea7ffc697c1d98926
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="19450-102">Gewusst wie: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="19450-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="19450-103">Im folgenden Verfahren und Beispiel wird veranschaulicht, wie eine verwaltete Anwendung den Handlewert für jedes Fenster auf dem lokalen Computer mithilfe eines Plattformaufrufs drucken kann.</span><span class="sxs-lookup"><span data-stu-id="19450-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="19450-104">Insbesondere verwenden das Verfahren und das Beispiel die **EnumWindows**-Funktion, um die Liste von Fenstern und eine verwaltete Rückruffunktion (namens „CallBack“) zu durchlaufen, um den Wert des Fensterhandles auszugeben.</span><span class="sxs-lookup"><span data-stu-id="19450-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="19450-105">So implementieren Sie die Rückruffunktion</span><span class="sxs-lookup"><span data-stu-id="19450-105">To implement a callback function</span></span>  
  
1.  <span data-ttu-id="19450-106">Betrachten Sie die Signatur für die **EnumWindows**-Funktion, bevor Sie mit der Implementierung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="19450-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="19450-107">**EnumWindows** weist die folgende Signatur auf:</span><span class="sxs-lookup"><span data-stu-id="19450-107">**EnumWindows** has the following signature:</span></span>  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     <span data-ttu-id="19450-108">Ein Hinweis darauf, dass diese Funktion einen Rückruf erfordert, ist das Vorkommen des **lpEnumFunc**-Arguments.</span><span class="sxs-lookup"><span data-stu-id="19450-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="19450-109">Es ist üblich, das Präfix **lp** (Long-Zeiger) zusammen mit dem Suffix **Func** im Namen von Argumenten zu sehen, die einen Zeiger auf eine Rückruffunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="19450-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="19450-110">Eine Dokumentation zu den Win32-Funktionen finden Sie im Microsoft Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="19450-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2.  <span data-ttu-id="19450-111">Erstellen Sie die verwaltete Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="19450-111">Create the managed callback function.</span></span> <span data-ttu-id="19450-112">Im Beispiel wird ein Delegattyp namens `CallBack` deklariert, der zwei Argumente übernimmt (**hwnd** und **lparam**).</span><span class="sxs-lookup"><span data-stu-id="19450-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="19450-113">Das erste Argument ist ein Handle für das Fenster. Das zweite Argument wird von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="19450-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="19450-114">In dieser Version müssen beide Argumente ganze Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="19450-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="19450-115">Rückruffunktionen geben im Allgemeinen bei einer erfolgreichen Ausführung einen Wert ungleich Null zurück, während ein Fehler durch 0 (null) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="19450-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="19450-116">In diesem Beispiel wird der Rückgabewert explizit auf **TRUE** festgelegt, um die Enumeration fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="19450-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3.  <span data-ttu-id="19450-117">Erstellen Sie einen Delegaten, und übergeben Sie ihn als Argument an die **EnumWindows**-Funktion.</span><span class="sxs-lookup"><span data-stu-id="19450-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="19450-118">Ein Plattformaufruf konvertiert den Delegaten automatisch in ein vertrautes Rückrufformat.</span><span class="sxs-lookup"><span data-stu-id="19450-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4.  <span data-ttu-id="19450-119">Stellen Sie sicher, dass der Garbage Collector den Delegaten nicht freigibt, bevor die Rückruffunktion ihre Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="19450-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="19450-120">Wenn Sie einen Delegaten als Parameter oder als in einer Struktur enthaltenes Feld übergeben, wird er für die Dauer des Aufrufs nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="19450-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="19450-121">Ebenso ist dies der Fall im folgenden Enumerationsbeispiel, in dem die Rückruffunktion ihre Arbeit beendet, bevor der Aufruf zurückkehrt. Daher erfordert sie keine zusätzliche Aktion des verwalteten Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="19450-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="19450-122">Wenn die Rückruffunktion jedoch nach der Rückkehr des Aufrufs aufgerufen werden kann, muss der verwaltete Aufrufer Maßnahmen ergreifen, um sicherzustellen, dass der Delegat weiterhin nicht erfasst wird, bevor die Rückruffunktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="19450-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="19450-123">Ausführliche Informationen zum Verhindern der Garbage Collection finden Sie unter [Interop-Marshalling](../../../docs/framework/interop/interop-marshaling.md) mit Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="19450-123">For detailed information about preventing garbage collection, see [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19450-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19450-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19450-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19450-125">See Also</span></span>  
 [<span data-ttu-id="19450-126">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="19450-126">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)  
 [<span data-ttu-id="19450-127">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="19450-127">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
