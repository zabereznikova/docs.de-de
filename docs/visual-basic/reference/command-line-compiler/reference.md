---
title: /reference (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f8c6851802afa818cc80b3f6d7eafc2ef47ac689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Bewirkt, dass der Compiler Typinformationen in den angegebenen Assemblys dem Projekt zur Verfügung, das Sie gerade kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
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
  
 Verwendung [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.  
  
 Für den Compiler an, das Erkennen eines Typs in einer Assembly (nicht in einem Modul) muss er gezwungen, den Typ aufzulösen. Ein Beispiel dafür, wie Sie dabei vorgehen können ist eine Instanz des Typs zu definieren. Weitere Möglichkeiten sind verfügbar, Typnamen in einer Assembly für den Compiler aufzulösen. Wenn Sie von einem Typ in einer Assembly erben, wird z. B. der Typnamen klicken Sie dann an den Compiler bezeichnet.  
  
 Die Antwortdatei "vbc.rsp", der Verweise häufig verwendet [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys, wird standardmäßig verwendet. Verwenden Sie `/noconfig` , wenn Sie nicht, dass den Compiler "vbc.rsp" zu verwenden möchten.  
  
 Die Kurzform von `/reference` ist `/r`.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert die Quelldatei `Input.vb` und Verweisassemblys aus `Metad1.dll` und `Metad2.dll`, um `Out.exe` zu produzieren.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
