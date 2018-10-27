---
title: -Warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 89f6566bd733ff92d464c026102429d3fc5cf0c1
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50047851"
---
# <a name="-warnaserror-visual-basic"></a>-Warnaserror (Visual Basic)
Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandelt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|+ &#124; -|Dies ist optional. In der Standardeinstellung `-warnaserror-` ist aktiviert; Warnungen verhindern nicht, dass den Compiler erzeugt eine Ausgabedatei. Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden.|  
|`numberList`|Dies ist optional. Durch Trennzeichen getrennte Liste von die Warnungs-ID-Nummern, die `-warnaserror` -Option gilt. Wenn keine Warnungs-ID angegeben wird, die `-warnaserror` Option gilt für alle Warnungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-warnaserror` Option werden alle Warnungen als Fehler behandelt. Alle Nachrichten, die normalerweise gemeldet worden wären, wie Warnungen stattdessen als Fehler gemeldet werden. Der Compiler meldet nachfolgende Vorkommen der gleichen Warnung als Warnungen.  
  
 In der Standardeinstellung `-warnaserror-` ist gültig, wodurch die Warnungen, um nur zu Informationszwecken sein. Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden.  
  
 Wenn Sie nur bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste mit Warnzahlen, die als Fehler behandelt angeben.  
  
> [!NOTE]
>  Die `-warnaserror` Option steuert nicht die Anzeige von Warnungen. Verwenden der [- Nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option aus, um Warnungen zu deaktivieren.  
  
|-Warnaserror, alle Warnungen als Fehler in der Visual Studio-IDE behandeln festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.<br />4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** Kontrollkästchen.|  
  
|-Warnaserror bestimmte Warnungen als Fehler in der Visual Studio-IDE behandelt festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.<br />4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.<br />5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden soll.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und weist den Compiler einen Fehler für das erste Vorkommen des jeder Warnung angezeigt, es findet.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
