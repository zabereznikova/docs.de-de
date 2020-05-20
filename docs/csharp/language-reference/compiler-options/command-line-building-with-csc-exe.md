---
title: Erstellen über die Befehlszeile mit csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: f692e66672b1804a309c6ac04c158af948a1b1ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789870"
---
# <a name="command-line-build-with-cscexe"></a>Erstellen über die Befehlszeile mit csc.exe

Sie können den C#-Compiler aufrufen, indem Sie den Namen seiner ausführbaren Datei (*csc.exe*) in der Befehlszeile eingeben.

Wenn Sie das Fenster **Developer-Eingabeaufforderung für Visual Studio** verwenden, werden alle erforderlichen Umgebungsvariablen für Sie festgelegt. Weitere Informationen zum Zugreifen auf dieses Tool finden Sie unter [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

Wenn Sie ein standardmäßiges Eingabeaufforderungsfenster verwenden, müssen Sie die Pfadangabe anpassen, bevor Sie *csc.exe* aus einem Unterverzeichnis auf dem Computer aufrufen können. Außerdem müssen Sie *vsvars32.bat* ausführen, um die entsprechenden Umgebungsvariablen zur Unterstützung von Befehlszeilenbuilds festzulegen. Weitere Informationen zu *vsvars32.bat*, einschließlich Anweisungen zum Suchen und Ausführen, finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).

Wenn Sie auf einem Computer arbeiten, auf dem nur das Windows Software Development Kit (SDK) installiert ist, können Sie den C#-Compiler an der **SDK-Eingabeaufforderung** verwenden. Diese öffnen Sie über die Menüoption **Microsoft .NET Framework SDK**.

Sie können auch MSBuild verwenden, um C#-Programme programmgesteuert zu erstellen. Weitere Informationen finden Sie unter [MSBuild](/visualstudio/msbuild/msbuild).

Die ausführbare Datei *csc.exe* befindet sich in der Regel im *Windows*-Verzeichnis im Ordner Microsoft.NET\Framework\\*\<Version>*. Der Speicherort unterscheidet sich je nach Konfiguration auf den einzelnen Computern. Wenn mehr als eine Version von .NET Framework auf dem Computer installiert ist, werden Sie mehrere Versionen dieser Datei finden. Weitere Informationen zu dieser Art von Installation finden Sie unter [How to: determine which versions of the .NET Framework are installed (Vorgehensweise: Bestimmen der installierten .NET Framework-Version)](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).

> [!TIP]
> Wenn Sie ein Projekt mit der Visual Studio-IDE erstellen, können Sie den Befehl **csc** und seine zugeordneten Compileroptionen im Fenster **Ausgabe** anzeigen. Um diese Informationen anzuzeigen, befolgen Sie die Anweisungen in [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log), in denen erläutert wird, wie der Ausführlichkeitsgrad der Protokolldaten in **Normal** oder **Detailliert** geändert wird. Nachdem Sie das Projekt neu erstellt haben, durchsuchen Sie das Fenster **Ausgabe** nach **csc** nach, um den Aufruf des C#-Compilers zu finden.

 **In diesem Thema**

- [Regeln für die Syntax der Befehlszeile](#rules-for-command-line-syntax-for-the-c-compiler)

- [Beispielbefehlszeilen](#sample-command-lines-for-the-c-compiler)

- [Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a>Regeln für Befehlszeilensyntax für den C#-Compiler

Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der C#-Compiler die folgenden Regeln:

- Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.

- Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem verarbeitet, bevor es an das `argv`-Array im Programm übergeben wird.

- Eine in Anführungszeichen eingeschlossene Zeichenfolge ("Zeichenfolge") wird als einzelnes Argument interpretiert, auch wenn darin Leerräume enthalten sind. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.

- Wenn dem Anführungszeichen ein umgekehrter Schrägstrich (\\") vorangestellt wird, wird diese Zeichenfolge als literales Anführungszeichen (") interpretiert.

- Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.

- Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.

- Wenn ein doppeltes Anführungszeichen auf eine ungerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das Anführungszeichen wird durch den übrig gebliebenen umgekehrten Schrägstrich maskiert. Hierdurch wird dem `argv`-Array ein echtes Anführungszeichen hinzugefügt.

## <a name="sample-command-lines-for-the-c-compiler"></a>Beispielbefehlszeilen für den C#-Compiler

- Kompiliert *file.cs*, sodass *file.exe* entsteht:

  ```console
  csc File.cs
  ```

- Kompiliert *file.cs*, sodass *file.exe* entsteht:

  ```console
  csc -target:library File.cs
  ```

- Kompiliert *file.cs* und erstellt *my.exe*:

  ```console
  csc -out:My.exe File.cs
  ```

- Kompiliert alle C#-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und definiert das DEBUG-Symbol. Die Ausgabe lautet *File2.exe*:

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- Kompiliert alle C#-Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von *File2.dll* erstellt wird. Es werden weder Logo noch Warnungen angezeigt:

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- Kompiliert alle C#-Dateien im aktuellen Verzeichnis zu *Name.xyz* (eine DLL-Datei):

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a>Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe

Durch den Aufruf des C#-Compilers werden keine Objektdateien ( *.obj*) erstellt, stattdessen werden die Ausgabedateien direkt erstellt. Daher benötigt der C#-Compiler keinen Linker.

## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [C#-Compileroptionen alphabetisch sortiert](./listed-alphabetically.md)
- [C#-Compileroptionen nach Kategorien sortiert](./listed-by-category.md)
- [Main() und Befehlszeilenargumente](../../programming-guide/main-and-command-args/index.md)
- [Befehlszeilenargumente](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [Vorgehensweise: Anzeigen von Befehlszeilenargumenten](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [Main()-Rückgabewerte](../../programming-guide/main-and-command-args/main-return-values.md)
