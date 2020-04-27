---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351707"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|+ &#124; -|Dies ist optional. Standardmäßig ist `-warnaserror-` aktiviert, sodass Warnungen den Compiler nicht daran hindern, eine Ausgabedatei zu erstellen. Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.|  
|`numberList`|Dies ist optional. Mit Kommas als Trennzeichen getrennte Liste der Warnungs-ID-Nummern, für die die `-warnaserror`-Option gilt. Ist keine Warnungs-ID angegeben, gilt die `-warnaserror`-Option für alle Warnungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-warnaserror`-Option bewirkt, dass alle Warnungen als Fehler behandelt werden. Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet. Der Compiler meldet weitere Vorkommen derselben Warnung als Warnungen.  
  
 Standardmäßig ist `-warnaserror-` aktiv, sodass Warnungen nur als Informationen gemeldet werden. Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.  
  
 Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie eine durch Kommas als Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.  
  
> [!NOTE]
> Die `-warnaserror`-Option steuert nicht, wie Warnungen angezeigt werden. Verwenden Sie die [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)-Option, um Warnungen zu deaktivieren.  
  
|So legen Sie „-warnaserror“ so fest, dass alle Warnungen in der Visual Studio-IDE als Fehler behandelt werden|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.<br />4.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.|  
  
|So legen Sie „-warnaserror“ so fest, dass bestimmte Warnungen in der Visual Studio-IDE als Fehler behandelt werden|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.<br />4.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.<br />5.  Wählen Sie **Fehler** in der **Benachrichtigung**-Spalte neben der Warnung aus, die als Fehler behandelt werden soll.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird `In.vb` kompiliert und wird der Compiler angewiesen, für das erste Vorkommen jeder von ihm gefundenen Warnung einen Fehler anzuzeigen.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird `T2.vb` kompiliert und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
