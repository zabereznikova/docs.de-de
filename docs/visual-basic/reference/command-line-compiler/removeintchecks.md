---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: f061497083dc23fd07f61108938a4129c0af5f3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188529"
---
# <a name="-removeintchecks"></a>-removeintchecks
Aktiviert die Überlauf-fehlerüberprüfung für Ganzzahloperationen ein- oder ausschalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Die `-removeintchecks-` Option veranlasst den Compiler, alle integerberechnungen auf Ganzzahlüberlauf-Fehler zu überprüfen. Die Standardeinstellung ist `-removeintchecks-`.<br /><br /> Angeben von `-removeintchecks` oder `-removeintchecks+` verhindert die Überprüfung von Fehlern und können ganzzahlige Berechnungen zu beschleunigen. Allerdings ohne Überprüfung von Fehlern, und wenn datenkapazitäten auf Typ ist ein Überlauf aufgetreten sind, können falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgelöst.|  
  
|-Removeintchecks in der integrierten Entwicklungsumgebung von Visual Studio festlegen.|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` Ganzzahlüberlauf Überprüfung deaktiviert.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
