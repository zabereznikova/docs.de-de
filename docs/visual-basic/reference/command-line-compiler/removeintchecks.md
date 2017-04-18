---
title: / removeintchecks | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 8e50200b8755ccc6b1c173024856955f5075b67e
ms.lasthandoff: 03/13/2017

---
# <a name="removeintchecks"></a>/removeintchecks
Aktiviert die Ganzzahlüberlauf-Überprüfung für Ganzzahloperationen ein- oder ausschalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Die `/removeintchecks-` Option bewirkt, dass der Compiler alle ganzzahligen Berechnungen für Überlauffehler überprüfen. Die Standardeinstellung ist `/removeintchecks-`.<br /><br /> Angeben von `/removeintchecks` oder `/removeintchecks+` verhindert die Überprüfung von Fehlern und Ganzzahl Berechnungen schneller machen können. Allerdings ohne die Überprüfung von Fehlern, wenn Typ Datenkapazität überlaufen, möglicherweise falsche Ergebnisse ohne das Auslösen eines Fehlers gespeichert.|  
  
|Zum Festlegen von/removeintchecks in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie den Wert von der **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
