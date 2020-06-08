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
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400473"
---
# <a name="-removeintchecks"></a>-removeintchecks
Aktiviert oder deaktiviert die Überprüfung auf Überlauffehler für Integervorgänge  
  
## <a name="syntax"></a>Syntax  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Die Option `-removeintchecks-` bewirkt, dass der Compiler alle Integerberechnungen auf Überlauffehler prüft. Der Standardwert ist `-removeintchecks-`.<br /><br /> Wenn Sie `-removeintchecks` oder `-removeintchecks+` angeben, wird die Fehlerüberprüfung verhindert, und Integerberechnungen können beschleunigt werden. Ohne Fehlerüberprüfung und bei einem Überlauf der Datentypkapazitäten können jedoch falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgegeben wird.|  
  
|So legen Sie -removeintchecks in der Visual Studio-IDE fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie den Wert des Felds **Überprüfungen auf Ganzzahlüberlauf entfernen**.|  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `Test.vb` kompiliert, und die Überprüfung auf Überlauffehler für Integerwerte wird deaktiviert.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
