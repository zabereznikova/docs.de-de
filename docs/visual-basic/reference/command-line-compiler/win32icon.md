---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 52ef0b991554c800dba4320b0c64c81ddd1b0ff4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414284"
---
# <a name="-win32icon"></a>-win32icon
Diese Option fügt eine ICO-Datei in die Ausgabedatei ein. Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer** dar.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Hierbei handelt es sich um die ICO-Datei, die Sie Ihrer Ausgabedatei hinzufügen. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine ICO-Datei mit dem Microsoft Windows-Ressourcencompiler (RC) erstellen. Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine ICO-Datei erstellt. Die Optionen `-win32icon` und `-win32resource` schließen sich gegenseitig aus.  
  
 Weitere Informationen zum Verweis auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource (Visual Basic)](linkresource.md). Informationen zum Hinzufügen einer .NET Framework-Ressourcendatei finden Sie unter [-resource (Visual Basic)](resource.md). Weitere Informationen zum Importieren einer RES-Datei finden Sie unter [-win32resource](win32resource.md).  
  
|Festlegen der -win32icon-Option in der Visual Studio-IDE|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert im Feld **Symbol**.|  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code werden `In.vb` kompiliert und eine ICO-Datei (`Rf.ico`) angefügt.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
