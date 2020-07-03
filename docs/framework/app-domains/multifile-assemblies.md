---
title: Mehrfachdateiassemblys
description: Verwenden Sie Mehrfachdateiassemblys, die auf .NET ausgerichtet sind, mithilfe des Befehlszeilencompilers oder in Visual Studio mit Visual C++. Eine Datei in der Assembly muss das Assemblymanifest enthalten.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104632"
---
# <a name="multifile-assemblies"></a>Mehrfachdateiassemblys

Sie können Mehrfachdateiassemblys für das .NET Framework mit Befehlszeilencompiler oder mit Visual Studio und Visual C++ erstellen. Eine Datei in der Assembly muss das Assemblymanifest enthalten. Eine Assembly, die eine Anwendung startet, muss außerdem einen Einstiegspunkt wie z. B. die Methoden `Main` oder `WinMain` enthalten.

Angenommen, Sie verfügen über eine Anwendung, die die beiden Codemodule *Client.cs* und *Stringer.cs* enthält. *Stringer.cs* erstellt den `myStringer`-Namespace, auf den im Code von *Client.cs* verwiesen wird. *Client.cs* enthält die `Main`-Methode, die der Einstiegspunkt der Anwendung ist. In diesem Beispiel kompilieren Sie die zwei Codemodule und erstellen dann eine dritte Datei, die das Assemblymanifest enthält, das die Anwendung startet. Das Assemblymanifest verweist sowohl auf das Modul *Client* als auch auf *Stringer*.

> [!NOTE]
> Mehrfachdateiassemblys können nur einen Einstiegspunkt haben, auch wenn die Assembly über mehrere Codemodule verfügt.

Es gibt mehrere Gründe, sich für eine Mehrfachdateiassembly zu entscheiden:

- Das Kombinieren von Modulen, die in unterschiedlichen Sprachen geschrieben wurden. Dies ist der häufigste Grund für das Erstellen einer Mehrfachdateiassembly.

- Die Optimierung des Herunterladens einer Anwendung durch das Einfügen selten verwendeter Typen in ein Modul, das nur wenn nötig heruntergeladen wird.

    > [!NOTE]
    > Wenn Sie eine Anwendung erstellen, die mit dem `<object>`-Tag mit Microsoft Internet Explorer heruntergeladen wird, ist es wichtig, dass Sie Mehrfachdateiassemblys erstellen. In diesem Szenario erstellen Sie eine von Ihren Codemodulen getrennte Datei, die nur das Assemblymanifest enthält. Internet Explorer lädt zunächst das Assemblymanifest herunter und erstellt anschließend Arbeitsthreads, um alle weiteren erforderlichen Module bzw. Assemblys herunterzuladen. Während des Downloads der Datei, die das Assemblymanifest enthält, reagiert Internet Explorer nicht auf Eingaben des Benutzers. Je kleiner die Datei ist, die das Assemblymanifest enthält, desto kürzer ist die Zeitspanne, in der Internet Explorer nicht reagiert.

- Das Kombinieren von Codemodulen, die von mehreren Entwicklern geschrieben wurden. Obwohl jeder Entwickler jedes Codemodul in eine Assembly kompilieren kann, kann dies dazu führen, dass einige Teile öffentlich gemacht werden, die aber nicht verfügbar gemacht werden, wenn alle Module in eine Mehrfachdateiassembly integriert werden.

Sobald Sie die Assembly erstellt haben, können Sie die Datei signieren, die das Assemblymanifest enthält. Dadurch wird gleichzeitig die Assembly signiert. Alternativ können Sie der Datei und der Assembly auch einen starken Namen geben und sie in den globalen Assemblycache einfügen.

## <a name="see-also"></a>Siehe auch

- [How to: Erstellen einer Mehrfachdateiassembly](build-multifile-assembly.md)
- [Programmieren mit Assemblys](../../standard/assembly/index.md)
