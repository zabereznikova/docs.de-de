---
title: 'Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 69c95289f91f712bd3fda03a7f582d879141591a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)
Sie können den Befehlszeilencompiler aufrufen, durch den Namen seiner ausführbaren Datei in der Befehlszeile angeben, auch bekannt als MS-DOS. Wenn Sie über die Standard-Windows-Befehlszeile kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben. Um dieses Standardverhalten zu überschreiben, können Sie entweder die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] -Eingabeaufforderungsfenster aus, oder ändern Sie die PATH-Umgebungsvariable. Beide ermöglichen es Ihnen, einfach den Compilernamen aus dem Verzeichnis zu kompilieren.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Zum Aufrufen des Compilers mithilfe der Visual Studio-Befehlszeile  
  
1.  Öffnen Sie den Programmordner von Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio.  
  
2.  Sie können die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Befehlszeile aus, um den Compiler aus dem Verzeichnis auf Ihrem Computer zugreifen, wenn Visual Studio installiert ist.  
  
3.  Aufrufen der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Eingabeaufforderungsfenster.  
  
4.  Geben Sie an der Befehlszeile `vbc.exe` *SourceFileName* und drücken Sie dann die EINGABETASTE.  
  
     Beispielsweise, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Befehlszeile und den Typ `cd SourceFiles` in dieses Verzeichnis zu ändern. Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Die PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Befehlszeile  
  
1.  Verwenden Sie die Windows-Suchfunktion Vbc.exe auf dem lokalen Datenträger gefunden.  
  
     Der genaue Name des Verzeichnisses, in dem der Compiler befindet, hängt von den Speicherort des Windows-Verzeichnisses und die Version der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installiert. Wenn Sie mehr als eine Version von ist die [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installiert haben, müssen Sie bestimmen, welche Version verwendet (in der Regel die neueste Version).  
  
2.  Aus der **Start** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.  
  
3.  Klicken Sie auf die **erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.  
  
4.  In der **System** Variablen Bereich **Pfad** aus der Liste aus und klicken Sie auf **bearbeiten**.  
  
5.  In der **bearbeiten** Variable Dialogfeld verschieben Sie die Einfügemarke an das Ende der Zeichenfolge in der **Variablenwert** aus, und geben Sie ein Semikolon (;) gefolgt vom vollständigen Verzeichnisnamen aus Schritt 1.  
  
6.  Klicken Sie auf **OK** Ihre Änderungen zu bestätigen und das Dialogfeld zu schließen.  
  
     Nachdem Sie die PATH-Umgebungsvariable geändert haben, können Sie Ausführen den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler an der Windows-Befehlszeile aus dem Verzeichnis auf dem Computer.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Zum Aufrufen des Compilers mithilfe der Windows-Befehlszeile  
  
1.  Aus der **Start** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie die **Windows-Befehlszeile**.  
  
2.  Geben Sie an der Befehlszeile `vbc.exe` *SourceFileName* und drücken Sie dann die EINGABETASTE.  
  
     Beispielsweise, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Befehlszeile und den Typ `cd SourceFiles` in dieses Verzeichnis zu ändern. Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
