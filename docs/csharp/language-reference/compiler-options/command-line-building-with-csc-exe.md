---
title: "Erstellen &#252;ber die Befehlszeile mit csc.exe | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Builds [C#]"
  - "Befehlszeile [C#]"
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Erstellen &#252;ber die Befehlszeile mit csc.exe
Sie können den C#-Compiler aufrufen, indem Sie den Namen seiner ausführbaren Datei (CSC.EXE) an der Befehlszeile eingeben.  
  
 Bei Verwendung der **Visual Studio Command Prompt** Fenster alle erforderlichen Umgebungsvariablen für Sie festgelegt. In Windows 7 können Sie das Fenster aus zugreifen die **Start** Menü öffnen Sie Microsoft Visual Studio *Version*\Visual Studio-Tools-Ordner. In Windows 8, die Visual Studio-Eingabeaufforderungsfenster wird aufgerufen, die **Developer-Eingabeaufforderung für VS2012**, und suchen Sie im Startbildschirm finden.  
  
 Wenn Sie ein standardmäßiges Eingabeaufforderungsfenster verwenden, müssen Sie die Pfadangabe anpassen, bevor Sie CSC.EXE aus einem Unterverzeichnis auf dem Computer aufrufen können. Außerdem müssen Sie "vsvars32.bat" ausführen, um die entsprechenden Umgebungsvariablen zur Unterstützung von Befehlszeilenbuilds festzulegen. Weitere Informationen zu VSVARS32, einschließlich Anweisungen zum Suchen und ausführen, finden Sie unter [Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Wenn Sie auf einem Computer arbeiten, der nur die [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong-md.md)], können Sie den C#-Compiler von der **SDK Command Prompt**, das Sie öffnen die **Microsoft .NET Framework SDK** Menüoption.  
  
 Sie können auch MSBuild verwenden, um C#-Programme programmgesteuert zu erstellen. Weitere Informationen finden Sie unter [MSBuild](/visual-studio/msbuild/msbuild1).  
  
 Die ausführbare Datei csc.exe befindet sich in der Microsoft.NET\Framework"\\*Version* Ordner im Windows-Verzeichnis. Der Speicherort unterscheidet sich je nach Konfiguration auf den einzelnen Computern. Wenn mehr als eine Version von .NET Framework auf dem Computer installiert ist, werden Sie mehrere Versionen dieser Datei finden. Weitere Informationen zu dieser Art von Installation, finden Sie unter [bestimmen die Version der .NET Framework installiert ist](http://msdn.microsoft.com/de-de/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c).  
  
> [!TIP]
>  Wenn Sie ein Projekt mithilfe von Visual Studio-IDE erstellen, können Sie Anzeigen der **csc** Befehl und seine zugeordneten Compileroptionen in die **Ausgabe** Fenster. Um diese Informationen anzuzeigen, führen Sie die Schritte [Gewusst wie: anzeigen, speichern und erstellen Sie Protokolldateien konfigurieren](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md) So ändern Sie den Ausführlichkeitsgrad der Protokolldaten in **Normal** oder **detailliert**. Nachdem Sie das Projekt neu erstellen, durchsuchen die **Ausgabe** Fenster für **csc** an den Aufruf des C#-Compilers zu finden.  
  
 **In diesem Thema**  
  
-   [Regeln für Befehlszeilensyntax](#vcconcommand-linebuildinganchor1)  
  
-   [Beispielbefehlszeilen](#vcconcommand-linebuildinganchor2)  
  
-   [Unterschiede zwischen der C#-Compiler und C++-Compiler-Ausgabe](#vcconcommand-linebuildinganchor3)  
  
##  <a name="a-namevcconcommand-linebuildinganchor1a-rules-for-command-line-syntax-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor1"></a> Regeln für Befehlszeilensyntax für den C#-Compiler  
 Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der C#-Compiler die folgenden Regeln:  
  
-   Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.  
  
-   Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem verarbeitet, bevor es an das argv-Array im Programm übergeben wird.  
  
-   Eine in Anführungszeichen eingeschlossene Zeichenfolge ("Zeichenfolge") wird als einzelnes Argument interpretiert, auch wenn darin Leerräume enthalten sind. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.  
  
-   Ein doppeltes Anführungszeichen ein umgekehrter Schrägstrich vorangestellt (\\") wird als ein Zeichen literales Anführungszeichen (") interpretiert.  
  
-   Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im argv-Array platziert. Das Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine ungerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im argv-Array platziert. Das Anführungszeichen wird durch den übrig gebliebenen umgekehrten Schrägstrich maskiert. Hierdurch wird dem argv-Array ein echtes Anführungszeichen hinzugefügt.  
  
##  <a name="a-namevcconcommand-linebuildinganchor2a-sample-command-lines-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor2"></a> Beispielbefehlszeilen für den C#-Compiler  
  
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
  
##  <a name="a-namevcconcommand-linebuildinganchor3a-differences-between-c-compiler-and-c-compiler-output"></a><a name="vcconcommand-linebuildinganchor3"></a> Unterschiede zwischen der C#-Compiler und C++-Compiler-Ausgabe  
 Durch den Aufruf des C#-Compilers werden keine Objektdateien (OBJ-Dateien) erstellt, stattdessen werden die Ausgabedateien direkt erstellt. Daher benötigt der C#-Compiler keinen Linker.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [C#-Compileroptionen alphabetisch sortiert](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [C#-Compileroptionen nach Kategorien sortiert](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [Gewusst wie: Anzeigen der Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Gewusst wie: Zugriff Befehlszeilenargumente mithilfe von Foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)