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
# <a name="debugging-stackoverflow-errors"></a>Debuggen von StackOverflow-Fehlern

Eine <xref:System.StackOverflowException>-Ausnahme wird bei einem Überlauf des Ausführungsstapels durch zu viele geschachtelte Methodenaufrufe ausgelöst.  

Nehmen Sie beispielsweise an, Sie hätten folgende App:

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

Die Main-Methode wird fortlaufend aufgerufen, bis kein Stapelspeicher mehr vorhanden ist.  Wenn kein Stapelspeicher mehr vorhanden ist, kann die Ausführung nicht fortgesetzt werden, und es wird eine <xref:System.StackOverflowException>-Ausnahme ausgelöst.  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> Bei .NET 5 und höher wird die Aufrufliste an die Konsole ausgegeben.

> [!NOTE]
> In diesem Artikel wird beschrieben, wie Sie einen Stapelüberlauf mit lldb debuggen. Wenn die Ausführung unter Windows erfolgt, empfiehlt es sich, die App mit [Visual Studio](/visualstudio/debugger/what-is-debugging) oder [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) zu debuggen.  

## <a name="example"></a>Beispiel

1. Ausführen der App mit der Konfiguration zum Sichern eines Absturzabbilds

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. Installieren der SOS-Erweiterung mithilfe von [dotnet-sos](dotnet-sos.md)

    ````
    dotnet-sos install
    ````

3. Debuggen des Abbilds in lldb, um den fehlerhaften Stapel anzuzeigen

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

4. Der obere Frame `0x00007f59b40900cc` wird mehrmals wiederholt. Verwenden Sie den [SOS-](sos-debugging-extension.md) `ip2md`-Befehl, um herauszufinden, welche Methode sich unter der `0x00007f59b40900cc`-Adresse befindet.

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

5. Sehen Sie sich die angegebene Methode „temp.Program.Main(System.String[])“ und die Quelle „/temp/Program.cs @ 9“ an, um zu ermitteln, ob Sie feststellen können, was Sie falsch gemacht haben. Wenn es immer noch nicht klar ist, können Sie die Protokollierung in diesem Bereich des Codes hinzufügen.

## <a name="see-also"></a>Weitere Informationen

* [Eine Einführung in Speicherabbilder in .NET](dumps.md)
* [Debuggen von Linux-Sicherungskopien](debug-linux-dumps.md)
* [SOS-Debugerweiterung für .NET](sos-debugging-extension.md)
