---
title: -Verweis (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-reference-visual-basic"></a>-Verweis (Visual Basic)
Bewirkt, dass der Compiler Typinformationen in den angegebenen Assemblys dem Projekt zur Verfügung, das Sie gerade kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileList`|Erforderlich. Durch Trennzeichen getrennte Liste von Assemblydateinamen. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die zu importierenden Dateien müssen Assemblymetadaten enthalten. Nur öffentliche Typen, die außerhalb der Assembly sichtbar sind. Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) Option importiert Metadaten aus einem Modul.  
  
 Wenn Sie eine Assembly (Assembly A) verweisen, die selbst verweist auf eine andere Assembly (Assembly B), müssen Sie die Referenz Assembly B wenn:  
  
-   Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
-   Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.  
  
 Verwendung [- Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.  
  
 Für den Compiler an, das Erkennen eines Typs in einer Assembly (nicht in einem Modul) muss er gezwungen, den Typ aufzulösen. Ein Beispiel dafür, wie Sie dabei vorgehen können ist eine Instanz des Typs zu definieren. Weitere Möglichkeiten sind verfügbar, Typnamen in einer Assembly für den Compiler aufzulösen. Wenn Sie von einem Typ in einer Assembly erben, wird z. B. der Typnamen klicken Sie dann an den Compiler bezeichnet.  
  
 Die Antwortdatei "vbc.rsp", der Verweise häufig verwendet [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys, wird standardmäßig verwendet. Verwenden Sie `-noconfig` , wenn Sie nicht, dass den Compiler "vbc.rsp" zu verwenden möchten.  
  
 Die Kurzform von `-reference` ist `/r`.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert die Quelldatei `Input.vb` und verweisen auf Assemblys von `Metad1.dll` und `Metad2.dll` erzeugt `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [-Ziel (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
