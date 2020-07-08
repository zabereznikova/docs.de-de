---
title: 'Vorgehensweise: Implementieren von Rückruffunktionen'
description: Erfahren Sie mehr zum Implementieren von Rückruffunktionen. In diesem Beispiel gibt eine verwaltete Anwendung mittels Plattformaufruf den Handlewert jedes Fensters auf einem Computer aus.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
ms.openlocfilehash: 31c657372e760c8d57f9714b20178967ad85fcd3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619116"
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="9c2ba-104">Vorgehensweise: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="9c2ba-104">How to: Implement Callback Functions</span></span>
<span data-ttu-id="9c2ba-105">Im folgenden Verfahren und Beispiel wird veranschaulicht, wie eine verwaltete Anwendung den Handlewert für jedes Fenster auf dem lokalen Computer mithilfe eines Plattformaufrufs drucken kann.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-105">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="9c2ba-106">Insbesondere verwenden das Verfahren und das Beispiel die **EnumWindows**-Funktion, um die Liste von Fenstern und eine verwaltete Rückruffunktion (namens „CallBack“) zu durchlaufen, um den Wert des Fensterhandles auszugeben.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-106">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="9c2ba-107">So implementieren Sie die Rückruffunktion</span><span class="sxs-lookup"><span data-stu-id="9c2ba-107">To implement a callback function</span></span>  
  
1. <span data-ttu-id="9c2ba-108">Betrachten Sie die Signatur für die **EnumWindows**-Funktion, bevor Sie mit der Implementierung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-108">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="9c2ba-109">**EnumWindows** weist die folgende Signatur auf:</span><span class="sxs-lookup"><span data-stu-id="9c2ba-109">**EnumWindows** has the following signature:</span></span>  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     <span data-ttu-id="9c2ba-110">Ein Hinweis darauf, dass diese Funktion einen Rückruf erfordert, ist das Vorkommen des **lpEnumFunc**-Arguments.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-110">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="9c2ba-111">Es ist üblich, das Präfix **lp** (Long-Zeiger) zusammen mit dem Suffix **Func** im Namen von Argumenten zu sehen, die einen Zeiger auf eine Rückruffunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-111">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="9c2ba-112">Eine Dokumentation zu den Win32-Funktionen finden Sie im Microsoft Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-112">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2. <span data-ttu-id="9c2ba-113">Erstellen Sie die verwaltete Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-113">Create the managed callback function.</span></span> <span data-ttu-id="9c2ba-114">Im Beispiel wird ein Delegattyp namens `CallBack` deklariert, der zwei Argumente übernimmt (**hwnd** und **lparam**).</span><span class="sxs-lookup"><span data-stu-id="9c2ba-114">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="9c2ba-115">Das erste Argument ist ein Handle für das Fenster. Das zweite Argument wird von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-115">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="9c2ba-116">In diesem Release müssen beide Argumente ganze Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-116">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="9c2ba-117">Rückruffunktionen geben im Allgemeinen bei einer erfolgreichen Ausführung einen Wert ungleich Null zurück, während ein Fehler durch 0 (null) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-117">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="9c2ba-118">In diesem Beispiel wird der Rückgabewert explizit auf **TRUE** festgelegt, um die Enumeration fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-118">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3. <span data-ttu-id="9c2ba-119">Erstellen Sie einen Delegaten, und übergeben Sie ihn als Argument an die **EnumWindows**-Funktion.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-119">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="9c2ba-120">Ein Plattformaufruf konvertiert den Delegaten automatisch in ein vertrautes Rückrufformat.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-120">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4. <span data-ttu-id="9c2ba-121">Stellen Sie sicher, dass der Garbage Collector den Delegaten nicht freigibt, bevor die Rückruffunktion ihre Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-121">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="9c2ba-122">Wenn Sie einen Delegaten als Parameter oder als in einer Struktur enthaltenes Feld übergeben, wird er für die Dauer des Aufrufs nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-122">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="9c2ba-123">Ebenso ist dies der Fall im folgenden Enumerationsbeispiel, in dem die Rückruffunktion ihre Arbeit beendet, bevor der Aufruf zurückkehrt. Daher erfordert sie keine zusätzliche Aktion des verwalteten Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-123">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="9c2ba-124">Wenn die Rückruffunktion jedoch nach der Rückkehr des Aufrufs aufgerufen werden kann, muss der verwaltete Aufrufer Maßnahmen ergreifen, um sicherzustellen, dass der Delegat weiterhin nicht erfasst wird, bevor die Rückruffunktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-124">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="9c2ba-125">Ausführliche Informationen zum Verhindern der Garbage Collection finden Sie unter [Interop-Marshalling](interop-marshaling.md) mit Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="9c2ba-125">For detailed information about preventing garbage collection, see [Interop Marshaling](interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c2ba-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c2ba-126">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c2ba-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c2ba-127">See also</span></span>

- [<span data-ttu-id="9c2ba-128">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="9c2ba-128">Callback Functions</span></span>](callback-functions.md)
- [<span data-ttu-id="9c2ba-129">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="9c2ba-129">Calling a DLL Function</span></span>](calling-a-dll-function.md)
