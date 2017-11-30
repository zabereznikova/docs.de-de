---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a>/removeintchecks
Aktiviert die Überlauf-Fehler beim Überprüfen der für Ganzzahloperationen ein- oder ausschalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Die `/removeintchecks-` Option veranlasst den Compiler, überprüfen Sie alle Ganzzahl Berechnungen auf Ganzzahlüberlauf-Fehler. Die Standardeinstellung ist `/removeintchecks-`.<br /><br /> Angeben von `/removeintchecks` oder `/removeintchecks+` verhindert die Überprüfung von Fehlern und Integer Berechnungen schneller machen können. Allerdings ohne Überprüfung von Fehlern, und wenn der Typ der Datenkapazität überlaufen, möglicherweise falsche Ergebnisse gespeichert werden, ohne einen Fehler auszulösen.|  
  
|Zum Festlegen von/removeintchecks in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
