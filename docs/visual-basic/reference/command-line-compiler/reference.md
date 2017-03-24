---
title: / Reference (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 12344dba82131d6be2c32127de287a6e9e3efa39
ms.lasthandoff: 03/13/2017

---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Veranlasst den Compiler, Typinformationen in den angegebenen Assemblys für das Projekt verfügbar, das Sie gerade kompilieren.  
  
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
 Die importierten Dateien müssen Assemblymetadaten enthalten. Es werden nur öffentliche Typen außerhalb der Assembly sichtbar. Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) -Option importiert Metadaten aus einem Modul.  
  
 Wenn Sie eine Assembly (Assembly A) verweisen, die wiederum verweist auf eine andere Assembly (Assembly B), müssen Sie auf Assembly B verweisen wenn:  
  
-   Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
-   Ein Feld, Eigenschaft, Ereignis oder -Methode, die einen Rückgabetyp für oder Parametertyp aus Assembly B wird aufgerufen.  
  
 Verwendung [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.  
  
 Der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennt muss er gezwungen werden, den Typ aufzulösen. Ein Beispiel dafür, wie Sie dies tun können, ist eine Instanz des Typs zu definieren. Andere Methoden sind auflösen Typnamen in einer Assembly für den Compiler verfügbar. Wenn Sie von einem Typ in einer Assembly erben, wird der Name z. B. dann an den Compiler bezeichnet.  
  
 Der Vbc.rsp-Antwortdatei, die häufig Verweise verwendet [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys wird standardmäßig verwendet. Verwenden Sie `/noconfig` , wenn Sie nicht, dass den Compiler Vbc.rsp verwendet möchten.  
  
 Die Kurzform der `/reference` ist `/r`.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert Quelldatei I`nput.vb` und verweisen auf Assemblys von M`etad1.dll` und M`etad2.dll` zu O`ut.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
