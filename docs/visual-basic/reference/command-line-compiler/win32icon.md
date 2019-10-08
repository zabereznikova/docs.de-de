---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004642"
---
# <a name="-win32icon"></a>-win32icon
Fügt eine ICO-Datei in die Ausgabedatei ein. Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer**dar.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Die ICO-Datei, die der Ausgabedatei hinzugefügt werden soll. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Mit dem Microsoft Windows-Ressourcen Compiler (RC) können Sie eine ICO-Datei erstellen. Der Ressourcen Compiler wird aufgerufen, wenn Sie ein visuelles C++ Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt. Die Optionen "`-win32icon`" und "`-win32resource`" schließen sich gegenseitig aus.  
  
 Weitere Informationen zum Hinzufügen einer .NET Framework Ressourcen Datei finden [Visual Basic](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework Sie unter [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) . Weitere Informationen finden Sie unter win32resource, um eine res [-](../../../visual-basic/reference/command-line-compiler/win32resource.md) Datei zu importieren.  
  
|To Set-win32icon in der Visual Studio-IDE|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert im Feld **Symbol** .|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `In.vb` und fügt eine ICO-Datei an, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
