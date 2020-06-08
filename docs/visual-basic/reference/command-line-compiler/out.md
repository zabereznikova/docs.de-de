---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 75f3ee7f24112f911803732ccb8d39eeafa95e3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400512"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Gibt den Namen der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ausgabedatei, die vom Compiler erstellt wird. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie den vollständigen Namen und die Erweiterung der Datei an, die erstellt werden soll. Wenn Sie das nicht tun, wird der Name der EXE-Datei aus der Quellcodedatei mit der `Sub Main`-Prozedur und der Name der DLL-Datei aus der ersten Quellcodedatei abgeleitet.  
  
 Wenn Sie einen Dateinamen ohne EXE- oder DLL-Erweiterung angeben, fügt der Compiler die Erweiterung automatisch hinzu. Dabei ist entscheidend, welcher Wert für die `-target`-Compileroption angegeben wurde.  
  
|So legen Sie -out in der Visual Studio-IDE fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert im Feld **Assemblyname**.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-target (Visual Basic)](target.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
