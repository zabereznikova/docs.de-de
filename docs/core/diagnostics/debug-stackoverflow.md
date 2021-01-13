---
title: Debuggen von StackOverflow-Fehlern
description: In diesem Artikel erfahren Sie, wie Sie StackOverflow-Ausnahmen diagnostizieren können.
ms.topic: tutorial
ms.date: 12/22/2020
ms.openlocfilehash: 92edf854ddcc2e778949d74eff1370cf27db25b4
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764928"
---
# <a name="debugging-stackoverflow-errors"></a><span data-ttu-id="c830c-103">Debuggen von StackOverflow-Fehlern</span><span class="sxs-lookup"><span data-stu-id="c830c-103">Debugging StackOverflow errors</span></span>

<span data-ttu-id="c830c-104">Eine <xref:System.StackOverflowException>-Ausnahme wird bei einem Überlauf des Ausführungsstapels durch zu viele geschachtelte Methodenaufrufe ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c830c-104">A <xref:System.StackOverflowException> is thrown when when the execution stack overflows because it contains too many nested method calls.</span></span>  

<span data-ttu-id="c830c-105">Nehmen Sie beispielsweise an, Sie hätten folgende App:</span><span class="sxs-lookup"><span data-stu-id="c830c-105">For example, suppose you have an app as follows:</span></span>

````
using System;

namespace temp
{
    class Program
    {
        static void Main(string[] args)
        {
            Main(args); // oops this recursion won't stop
        }
    }
}
````

<span data-ttu-id="c830c-106">Die Main-Methode wird fortlaufend aufgerufen, bis kein Stapelspeicher mehr vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c830c-106">The Main method will continuously call itself until there is no more stack space.</span></span>  <span data-ttu-id="c830c-107">Wenn kein Stapelspeicher mehr vorhanden ist, kann die Ausführung nicht fortgesetzt werden, und es wird eine <xref:System.StackOverflowException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c830c-107">Once there is no more stack space, execution cannot continue and so it will throw a <xref:System.StackOverflowException>.</span></span>  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> <span data-ttu-id="c830c-108">Bei .NET 5 und höher wird die Aufrufliste an die Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c830c-108">On .NET 5 and later, the callstack is output to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="c830c-109">In diesem Artikel wird beschrieben, wie Sie einen Stapelüberlauf mit lldb debuggen.</span><span class="sxs-lookup"><span data-stu-id="c830c-109">This article describes how to debug a stack overflow with lldb.</span></span> <span data-ttu-id="c830c-110">Wenn die Ausführung unter Windows erfolgt, empfiehlt es sich, die App mit [Visual Studio](/visualstudio/debugger/what-is-debugging) oder [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="c830c-110">If you are running on Windows, we suggest debugging the app with [Visual Studio](/visualstudio/debugger/what-is-debugging) or [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging).</span></span>  

## <a name="example"></a><span data-ttu-id="c830c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c830c-111">Example</span></span>

1. <span data-ttu-id="c830c-112">Ausführen der App mit der Konfiguration zum Sichern eines Absturzabbilds</span><span class="sxs-lookup"><span data-stu-id="c830c-112">Run the app with it configured to collect a dump on crash</span></span>

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. <span data-ttu-id="c830c-113">Installieren der SOS-Erweiterung mithilfe von [dotnet-sos](dotnet-sos.md)</span><span class="sxs-lookup"><span data-stu-id="c830c-113">Install the SOS extension using [dotnet-sos](dotnet-sos.md)</span></span>

    ````
    dotnet-sos install
    ````

3. <span data-ttu-id="c830c-114">Debuggen des Abbilds in lldb, um den fehlerhaften Stapel anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="c830c-114">Debug the dump in lldb to see the failing stack</span></span>

    ````
    lldb --core /temp/coredump.6412
    (lldb) bt
    ...
        frame #261930: 0x00007f59b40900cc
        frame #261931: 0x00007f59b40900cc
        frame #261932: 0x00007f59b40900cc
        frame #261933: 0x00007f59b40900cc
        frame #261934: 0x00007f59b40900cc
        frame #261935: 0x00007f5a2d4a080f libcoreclr.so`CallDescrWorkerInternal at unixasmmacrosamd64.inc:867
        frame #261936: 0x00007f5a2d3cc4c3 libcoreclr.so`MethodDescCallSite::CallTargetWorker(unsigned long const*, unsigned long*, int) at callhelpers.cpp:70
        frame #261937: 0x00007f5a2d3cc468 libcoreclr.so`MethodDescCallSite::CallTargetWorker(this=<unavailable>, pArguments=0x00007ffe8222e7b0, pReturnValue=0x0000000000000000, cbReturnValue=0) at callhelpers.cpp:604
        frame #261938: 0x00007f5a2d4b6182 libcoreclr.so`RunMain(MethodDesc*, short, int*, PtrArray**) [inlined] MethodDescCallSite::Call(this=<unavailable>, pArguments=<unavailable>) at callhelpers.h:468
    ...
    ````

4. <span data-ttu-id="c830c-115">Der obere Frame `0x00007f59b40900cc` wird mehrmals wiederholt.</span><span class="sxs-lookup"><span data-stu-id="c830c-115">The top frame `0x00007f59b40900cc` is repeated several times.</span></span> <span data-ttu-id="c830c-116">Verwenden Sie den [SOS-](sos-debugging-extension.md) `ip2md`-Befehl, um herauszufinden, welche Methode sich unter der `0x00007f59b40900cc`-Adresse befindet.</span><span class="sxs-lookup"><span data-stu-id="c830c-116">Use the [SOS](sos-debugging-extension.md) `ip2md` command to figure out what method is located at the `0x00007f59b40900cc` address</span></span>

    ````
    (lldb) ip2md 0x00007f59b40900cc
    MethodDesc:   00007f59b413ffa8
    Method Name:          temp.Program.Main(System.String[])
    Class:                00007f59b4181d40
    MethodTable:          00007f59b4190020
    mdToken:              0000000006000001
    Module:               00007f59b413dbf8
    IsJitted:             yes
    Current CodeAddr:     00007f59b40900a0
    Version History:
      ILCodeVersion:      0000000000000000
      ReJIT ID:           0
      IL Addr:            0000000000000000
         CodeAddr:           00007f59b40900a0  (MinOptJitted)
         NativeCodeVersion:  0000000000000000
    Source file:  /temp/Program.cs @ 9
    ````

5. <span data-ttu-id="c830c-117">Sehen Sie sich die angegebene Methode „temp.Program.Main(System.String[])“ und die Quelle „/temp/Program.cs @ 9“ an, um zu ermitteln, ob Sie feststellen können, was Sie falsch gemacht haben.</span><span class="sxs-lookup"><span data-stu-id="c830c-117">Go look at the indicated method temp.Program.Main(System.String[]) and source "/temp/Program.cs @ 9" to see if you can figure out what you did wrong.</span></span> <span data-ttu-id="c830c-118">Wenn es immer noch nicht klar ist, können Sie die Protokollierung in diesem Bereich des Codes hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c830c-118">If it still wasn't clear you could add logging in that area of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="c830c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c830c-119">See Also</span></span>

* [<span data-ttu-id="c830c-120">Eine Einführung in Speicherabbilder in .NET</span><span class="sxs-lookup"><span data-stu-id="c830c-120">An introduction to dumps in .NET</span></span>](dumps.md)
* [<span data-ttu-id="c830c-121">Debuggen von Linux-Sicherungskopien</span><span class="sxs-lookup"><span data-stu-id="c830c-121">Debug Linux dumps</span></span>](debug-linux-dumps.md)
* [<span data-ttu-id="c830c-122">SOS-Debugerweiterung für .NET</span><span class="sxs-lookup"><span data-stu-id="c830c-122">SOS Debugging Extension for .NET</span></span>](sos-debugging-extension.md)
