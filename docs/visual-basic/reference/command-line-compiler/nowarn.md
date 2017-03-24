---
title: / nowarn | Microsoft-Dokumentation
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
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 61b145a9eb95f5357c7aa2983a96c31e8f2cef6a
ms.lasthandoff: 03/13/2017

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
|`numberList`|Optional. Durch Kommas getrennte Liste von Warnung-ID-Nummern an, denen der Compiler unterdrücken soll. Wenn die Warnung IDs nicht angegeben sind, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `/nowarn` -Option bewirkt, dass den Compiler keine Warnungen generiert werden. Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung auf die `/nowarn` Option hinter dem Doppelpunkt. Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.  
  
 Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben. Wenn Sie BC42024, die Warnung für nicht verwendete lokale Variablen unterdrücken möchten, z. B. Geben Sie `/nowarn:42024`.  
  
 Weitere Informationen über die Warnung-ID-Nummern, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Zum Festlegen von/nowarn in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Wählen Sie die **alle Warnungen deaktivieren** Kontrollkästchen, um alle Warnungen deaktivieren.<br />     - oder -<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdownliste neben der Warnung.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und keine Warnungen angezeigt.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und die Warnung für nicht verwendete lokale Variablen (42024) wird nicht angezeigt.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
