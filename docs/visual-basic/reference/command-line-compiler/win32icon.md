---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045e621f0104c4c958d77d2443c1524b33410b7a
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "39221022"
---
# <a name="-win32icon"></a>-win32icon
Fügt eine ICO-Datei in die Ausgabedatei ein. Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer**.  
  
## <a name="syntax"></a>Syntax  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Die ICO-Datei Ihrer Ausgabedatei hinzufügen. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine ICO-Datei mit dem Microsoft Windows Resource-Compiler (RC) erstellen. Der Ressourcencompiler wird aufgerufen, wenn Sie ein Visual C++-Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt. Die `-win32icon` und `-win32resource` Optionen schließen sich gegenseitig.  
  
 Finden Sie unter [- Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) zum Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei. Finden Sie unter [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) um eine RES-Datei zu importieren.  
  
|Festzulegende - win32icon in der Visual Studio-IDE|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert in der **Symbol** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und fügt eine ICO-Datei, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
