---
title: -Warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c04bff4070b0f1c288c8853e5045fbf670d8e9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-warnaserror-visual-basic"></a>-Warnaserror (Visual Basic)
Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandeln.  
  
## <a name="syntax"></a>Syntax  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|+ &#124; -|Dies ist optional. Standardmäßig `-warnaserror-` ist faktisch; Warnungen verhindern nicht, dass den Compiler aus, erzeugt eine Ausgabedatei. Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.|  
|`numberList`|Dies ist optional. Durch Trennzeichen getrennte Liste von Warnungs-ID, der Nummern der `-warnaserror` Option gilt. Wenn Sie keine Warnung-ID angegeben ist, die `-warnaserror` Option gilt für alle Warnungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-warnaserror` Option, um alle Warnungen als Fehler behandelt. Alle Nachrichten, die in der Regel gemeldet worden wären, wie Warnungen stattdessen als Fehler gemeldet werden. Der Compiler meldet weitere Vorkommen des gleichen Warnung als Warnungen.  
  
 Standardmäßig `-warnaserror-` ist aktiv, wodurch die Warnungen, um nur Informationszwecken gemeldet werden soll. Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.  
  
 Wenn Sie nur einige bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste mit Warnungsnummern als Fehler behandeln angeben.  
  
> [!NOTE]
>  Die `-warnaserror` Option steuert nicht die Anzeige von Warnungen. Verwenden der [- Nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option zum Deaktivieren von Warnungen.  
  
|-Warnaserror, um alle Warnungen als Fehler in der Visual Studio-IDE behandeln festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.<br />4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** Kontrollkästchen.|  
  
|-Warnaserror behandelt bestimmte Warnungen als Fehler in der Visual Studio-IDE festlegen|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.<br />4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.<br />5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden sollen.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und leitet den Compiler einen Fehler für das erste Vorkommen des jede Warnung anzuzeigen, es findet.  
  
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
 [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
