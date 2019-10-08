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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005227"
---
# <a name="-removeintchecks"></a>-removeintchecks
Schaltet die Überlauf Fehlerüberprüfung für ganzzahlige Vorgänge ein oder aus.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Die Option `-removeintchecks-` bewirkt, dass der Compiler alle ganzzahligen Berechnungen auf Überlauf Fehler prüft. Die Standardeinstellung ist `-removeintchecks-`.<br /><br /> Wenn Sie `-removeintchecks` oder `-removeintchecks+` angeben, wird die Fehlerüberprüfung verhindert, und ganz Zahl Berechnungen können beschleunigt werden. Ohne Fehlerüberprüfung und bei einem Überlauf der Datentyp Kapazitäten können jedoch falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgegeben wird.|  
  
|Zum Festlegen von "-removeintchecks" in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie den Wert des Kontrollkästchens **ganzzahlige Überlauf entfernen** .|  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `Test.vb` kompiliert und die ganzzahlige Überlauf Fehlerüberprüfung deaktiviert.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
