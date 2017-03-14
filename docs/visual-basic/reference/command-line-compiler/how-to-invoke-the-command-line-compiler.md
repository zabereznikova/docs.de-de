---
title: "How to: Invoke the Command-Line Compiler (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "command-line arguments"
  - "vbc.exe"
  - "Visual Basic compiler, starting"
  - "command line, arguments"
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# How to: Invoke the Command-Line Compiler (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Zum Aufrufen des Befehlszeilencompilers geben Sie den Namen seiner ausführbaren Datei in der Befehlszeile ein \(auch als MS\-DOS\-Eingabeaufforderung bezeichnet\).  Wenn Sie in der Standard\-Windows\-Eingabeaufforderung kompilieren, müssen Sie den voll qualifizierten Pfad zur ausführbaren Datei eingeben.  Wenn Sie dieses Standardverhalten überschreiben möchten, können Sie entweder die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]\-Eingabeaufforderung verwenden oder die PATH\-Umgebungsvariable ändern.  In beiden Fällen können Sie in einem beliebigen Verzeichnis kompilieren, indem Sie einfach den Compilernamen eingeben.  
  
 [!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### So rufen Sie den Compiler mit der Visual Studio\-Eingabeaufforderung auf  
  
1.  Öffnen Sie den Programmordner von Visual Studio\-Tools innerhalb der Microsoft Visual Studio\-Programmgruppe.  
  
2.  Sie können die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Eingabeaufforderung können Sie den Compiler von einem beliebigen Computerverzeichnis zuzugreifen, wenn Visual Studio installiert ist.  
  
3.  Rufen Sie die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]\-Eingabeaufforderung auf.  
  
4.  Geben Sie in der Befehlszeile `vbc.exe` *Quelldateiname* ein, und drücken Sie dann die EINGABETASTE.  
  
     Wenn Sie den Quellcode z. B. in einem Verzeichnis mit dem Namen `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln.  Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthielte, könnten Sie die Datei durch Eingeben von `vbc.exe Source.vb` kompilieren.  
  
### So legen Sie die PATH\-Umgebungsvariable auf den Compiler für die Windows\-Eingabeaufforderung fest  
  
1.  Verwenden Sie das Windows\-Feature Suchen, um die Datei Vbc.exe auf der lokalen Festplatte zu finden.  
  
     Der genaue Name des Verzeichnisses, in dem sich der Compiler befindet, hängt vom Speicherort des Windows\-Verzeichnisses und der installierten Version von [!INCLUDE[Compact](~/includes/compact-md.md)] ab.  Wenn mehr als eine Version von [!INCLUDE[Compact](~/includes/compact-md.md)] installiert ist, müssen Sie festlegen, welche Version verwendet werden soll \(in der Regel die neueste Version\).  
  
2.  Klicken Sie im **Startmenü** mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann im Kontextmenü auf **Eigenschaften**.  
  
3.  Klicken Sie auf die Registerkarte **Erweitert** und dann auf **Umgebungsvariablen**.  
  
4.  Wählen Sie im Bereich **Systemvariablen** den Eintrag **Path** aus, und klicken Sie auf **Bearbeiten**.  
  
5.  Verschieben Sie im Dialogfeld **Systemvariable bearbeiten** die Einfügemarke an das Ende der Zeichenfolge im Feld **Variablenwert**, und geben Sie ein Semikolon \(;\) gefolgt vom vollständigen Verzeichnisnamen aus Schritt 1 ein.  
  
6.  Klicken Sie auf **OK**, um die Bearbeitung zu bestätigen und das Dialogfeld zu schließen.  
  
     Nachdem Sie die PATH\-Umgebungsvariable geändert haben, können Sie den [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler von einem beliebigen Verzeichnis auf dem Computer über die Windows\-Eingabeaufforderung ausführen.  
  
### So rufen Sie den Compiler mit der Windows\-Eingabeaufforderung auf  
  
1.  Klicken Sie im **Startmenü** auf den Ordner **Zubehör**, und öffnen Sie dann die **Windows\-Eingabeaufforderung**.  
  
2.  Geben Sie in der Befehlszeile `vbc.exe` *Quelldateiname* ein, und drücken Sie dann die EINGABETASTE.  
  
     Wenn Sie den Quellcode z. B. in einem Verzeichnis mit dem Namen `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln.  Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthielte, könnten Sie die Datei durch Eingeben von `vbc.exe Source.vb` kompilieren.  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)