---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8da27ea2f9f0a4d370928d70cda1a796b822d97c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn"></a>/nowarn
Unterdrückt die Compilerfunktion zum Generieren von Warnungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`numberList`|Dies ist optional. Durch Trennzeichen getrennte Liste von die Warnung-ID-Nummern, die der Compiler unterdrücken soll. Wenn die Warnung IDs nicht angegeben werden, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `/nowarn` Option bewirkt, dass der Compiler keine Warnungen generiert werden. Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung, die die `/nowarn` Option nach dem Doppelpunkt ausmacht. Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.  
  
 Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben. Geben Sie z. B. wenn BC42024, das die Warnung für nicht verwendete lokale Variablen, unterdrückt werden sollen `/nowarn:42024`.  
  
 Weitere Informationen über die Warnung-ID-Nummern, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Zum Festlegen von/nowarn in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Wählen Sie die **deaktivieren Sie alle Warnungen** Kontrollkästchen, um alle Warnungen zu deaktivieren.<br />     - oder -<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdownliste neben der Warnung.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und keine Warnungen angezeigt.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und die Warnungen für nicht verwendete lokale Variablen (42024) nicht angezeigt.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
