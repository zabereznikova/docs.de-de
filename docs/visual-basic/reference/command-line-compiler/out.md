---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352384"
---
# <a name="-out-visual-basic"></a>-Out (Visual Basic)
Gibt den Namen der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich Der Name der Ausgabedatei, die vom Compiler erstellt wird. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie den vollständigen Namen und die Erweiterung der zu erstellenden Datei an. Wenn Sie dies nicht tun, wird der Name der exe-Datei aus der Quell Code Datei mit der `Sub Main` Prozedur und die DLL-Datei aus der ersten Quell Code Datei abgeleitet.  
  
 Wenn Sie einen Dateinamen ohne Erweiterung ". exe" oder ". dll" angeben, fügt der Compiler die Erweiterung automatisch hinzu, je nachdem, welcher Wert für die `-target`-Compileroption angegeben wurde.  
  
|So richten Sie in der integrierten Entwicklungsumgebung von Visual Studio ein|  
|---|  
|1. Wählen Sie ein Projekt aus, das in **Projektmappen-Explorer**ausgewählt ist. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2. Klicken Sie auf die Registerkarte **Anwendung** .<br />3. ändern Sie den Wert im Feld AssemblyName.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
