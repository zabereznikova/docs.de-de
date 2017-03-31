---
title: "Erstellen über die Befehlszeile mit csc.exe | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa6dd9801a141ec430bc291302fe74c35057f117
ms.lasthandoff: 03/13/2017

---
# <a name="command-line-building-with-cscexe"></a>Erstellen über die Befehlszeile mit csc.exe
Sie können den C#-Compiler aufrufen, indem Sie den Namen seiner ausführbaren Datei (CSC.EXE) an der Befehlszeile eingeben.  
  
 Wenn Sie das Fenster **Visual Studio-Eingabeaufforderung** verwenden, werden alle erforderlichen Umgebungsvariablen für Sie festgelegt. In Windows 7 können Sie auf dieses Fenster über das Menü **Start** zugreifen, indem Sie den Ordner Microsoft Visual Studio *Version*\Visual Studio-Tools öffnen. In Windows 8 wird die Visual Studio-Eingabeaufforderung als **Developer-Eingabeaufforderung für VS2012** bezeichnet. Sie finden sie über die Suche im Startmenü.  
  
 Wenn Sie ein standardmäßiges Eingabeaufforderungsfenster verwenden, müssen Sie die Pfadangabe anpassen, bevor Sie CSC.EXE aus einem Unterverzeichnis auf dem Computer aufrufen können. Außerdem müssen Sie "vsvars32.bat" ausführen, um die entsprechenden Umgebungsvariablen zur Unterstützung von Befehlszeilenbuilds festzulegen. Weitere Informationen zu vsvars32.bat, einschließlich Anweisungen zum Suchen und Ausführen, finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Wenn Sie auf einem Computer arbeiten, auf dem nur das [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong_md.md)] installiert ist, können Sie den C#-Compiler von der **SDK-Eingabeaufforderung** aus verwenden. Diese öffnen Sie über die Menüoption **Microsoft .NET Framework SDK**.  
  
 Sie können auch MSBuild verwenden, um C#-Programme programmgesteuert zu erstellen. Weitere Informationen finden Sie unter [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild1).  
  
 Die ausführbare Datei „csc.exe“ befindet sich in der Regel im Windows-Verzeichnis im Ordner Microsoft.NET\Framework\\\*Version*. Der Speicherort unterscheidet sich je nach Konfiguration auf den einzelnen Computern. Wenn mehr als eine Version von .NET Framework auf dem Computer installiert ist, werden Sie mehrere Versionen dieser Datei finden. Weitere Informationen zu dieser Art von Installation finden Sie unter [Bestimmen der installierten .NET Framework-Version](http://msdn.microsoft.com/en-us/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c).  
  
> [!TIP]
>  Wenn Sie ein Projekt mit der Visual Studio-IDE erstellen, können Sie den Befehl **csc** und seine zugeordneten Compileroptionen im Fenster **Ausgabe** anzeigen. Um diese Informationen anzuzeigen, befolgen Sie die Anweisungen in [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7), in denen erläutert wird, wie der Ausführlichkeitsgrad der Protokolldaten in **Normal** oder **Detailliert** geändert wird. Nachdem Sie das Projekt neu erstellt haben, durchsuchen Sie das Fenster **Ausgabe** nach **csc** nach, um den Aufruf des C#-Compilers zu finden.  
  
 **Inhalt**  
  
-   [Regeln für die Syntax der Befehlszeile](#vcconcommand-linebuildinganchor1)  
  
-   [Beispielbefehlszeilen](#vcconcommand-linebuildinganchor2)  
  
-   [Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe](#vcconcommand-linebuildinganchor3)  
  
##  <a name="vcconcommand-linebuildinganchor1"></a> Regeln für Befehlszeilensyntax für den C#-Compiler  
 Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der C#-Compiler die folgenden Regeln:  
  
-   Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.  
  
-   Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem verarbeitet, bevor es an das argv-Array im Programm übergeben wird.  
  
-   Eine in Anführungszeichen eingeschlossene Zeichenfolge ("Zeichenfolge") wird als einzelnes Argument interpretiert, auch wenn darin Leerräume enthalten sind. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.  
  
-   Wenn dem Anführungszeichen ein umgekehrter Schrägstrich (\\") vorangestellt wird, wird diese Zeichenfolge als literales Anführungszeichen (") interpretiert.  
  
-   Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im argv-Array platziert. Das Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine ungerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im argv-Array platziert. Das Anführungszeichen wird durch den übrig gebliebenen umgekehrten Schrägstrich maskiert. Hierdurch wird dem argv-Array ein echtes Anführungszeichen hinzugefügt.  
  
##  <a name="vcconcommand-linebuildinganchor2"></a> Beispielbefehlszeilen für den C#-Compiler  
  
-   Kompiliert File.cs, sodass File.exe entsteht:  
  
    ```  
    csc File.cs   
    ```  
  
-   Kompiliert File.cs, sodass File.dll entsteht:  
  
    ```  
    csc /target:library File.cs  
    ```  
  
-   Kompiliert File.cs und erstellt My.exe:  
  
    ```  
    csc /out:My.exe File.cs  
    ```  
  
-   Kompiliert alle C#-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und definiert das DEBUG-Symbol. Die Ausgabe lautet File2.exe:  
  
    ```  
    csc /define:DEBUG /optimize /out:File2.exe *.cs  
    ```  
  
-   Kompiliert alle C#-Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von File2.dll erstellt wird. Es werden weder Logo noch Warnungen angezeigt:  
  
    ```  
    csc /target:library /out:File2.dll /warn:0 /nologo /debug *.cs  
    ```  
  
-   Kompiliert alle C#-Dateien im aktuellen Verzeichnis zu Something.xyz (einer DLL-Datei):  
  
    ```  
    csc /target:library /out:Something.xyz *.cs  
    ```  
  
##  <a name="vcconcommand-linebuildinganchor3"></a> Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe  
 Durch den Aufruf des C#-Compilers werden keine Objektdateien (OBJ-Dateien) erstellt, stattdessen werden die Ausgabedateien direkt erstellt. Daher benötigt der C#-Compiler keinen Linker.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [C#-Compileroptionen alphabetisch sortiert](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [C#-Compileroptionen nach Kategorien sortiert](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [Vorgehensweise: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
