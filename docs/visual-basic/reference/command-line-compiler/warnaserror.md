---
title: / warnaserror (Visual Basic) | Microsoft-Dokumentation
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
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
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
ms.openlocfilehash: 28f232b1ad8200455550f2f4c1204818c8b143ab
ms.lasthandoff: 03/13/2017

---
# <a name="warnaserror-visual-basic"></a>/warnaserror (Visual Basic)
Der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|+ &#124; -|Optional. In der Standardeinstellung `/warnaserror-` ist aktiviert; Warnungen verhindern nicht, dass den Compiler erzeugt eine Ausgabedatei. Die `/warnaserror` Option, die die gleiche wird als `/warnaserror+`, werden Warnungen als Fehler behandelt werden.|  
|`numberList`|Optional. Durch Kommas getrennte Liste der ID der Warnung auf die Zahlen der `/warnaserror` Option gilt. Wenn keine Warnung-ID angegeben wird, die `/warnaserror` Option gilt für alle Warnungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `/warnaserror` Option alle Warnungen als Fehler behandelt. Alle Nachrichten, die in der Regel gemeldet werden, wie Warnungen stattdessen als Fehler gemeldet werden. Der Compiler meldet nachfolgende Vorkommen der gleichen Warnung als Warnungen.  
  
 In der Standardeinstellung `/warnaserror-` ist gültig, wodurch die Warnungen, um nur zu Informationszwecken werden. Die `/warnaserror` Option, die die gleiche wird als `/warnaserror+`, werden Warnungen als Fehler behandelt werden.  
  
 Wenn Sie nur einige bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste von Warnungsnummern als Fehler behandelt angeben.  
  
> [!NOTE]
>  Die `/warnaserror` Option steuert nicht die Anzeige von Warnungen. Verwenden der [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option zum Deaktivieren von Warnungen.  
  
|/ Warnaserror behandelt alle Warnungen als Fehler in der Visual Studio-IDE fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.<br />4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** das Kontrollkästchen.|  
  
|Festlegen von/warnaserror, bestimmte Warnungen als Fehler in der Visual Studio-IDE zu behandeln.|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.<br />4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.<br />5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden soll.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und leitet den Compiler einen Fehler für das erste Vorkommen eines jeder Warnung anzeigen gefunden wird.  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und nur die Warnung für nicht verwendete lokale Variablen (42024) wird als Fehler behandelt.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
