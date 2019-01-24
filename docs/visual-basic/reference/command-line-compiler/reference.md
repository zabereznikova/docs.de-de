---
title: -Referenz (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 4c410fd7dcaae4e19043f5f858a2f75c69587311
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662269"
---
# <a name="-reference-visual-basic"></a>-Referenz (Visual Basic)
Veranlasst den Compiler Typinformationen in den angegebenen Assemblys für das Projekt verfügbar sein, auf denen Sie aktuell kompilieren.  
  
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
 Die Dateien, die Sie importieren, müssen Assemblymetadaten enthalten. Es sind nur öffentliche Typen außerhalb der Assembly sichtbar. Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) Option importiert Metadaten aus einem Modul.  
  
 Wenn Sie eine Assembly (Assembly A) verweisen, die ihrerseits auf einer anderen Assembly (Assembly B) verweist, müssen Sie auf Assembly B verweisen wenn:  
  
-   Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
-   Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.  
  
 Verwendung [- Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) auf das Verzeichnis anzugeben, in denen eine oder mehrere der Assemblyverweise befinden.  
  
 Für den Compiler an, das Erkennen eines Typs in einer Assembly (nicht in einem Modul) muss er gezwungen werden, den Typ aufzulösen. Ein Beispiel dafür, wie Sie dies tun können, ist eine Instanz des Typs definieren. Weitere Möglichkeiten sind verfügbar, Typnamen in einer Assembly für den Compiler aufzulösen. Wenn Sie von einem Typ in einer Assembly erben, wird z. B. der Typnamen klicken Sie dann an den Compiler bezeichnet.  
  
 Der Vbc.rsp-Antwortdatei, die Verweise häufig verwendet [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys wird standardmäßig verwendet. Verwenden Sie `-noconfig` Wenn Sie nicht, dass den Compiler "vbc.rsp" zu verwenden möchten.  
  
 Die Kurzform von `-reference` ist `/r`.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert die Quelldatei `Input.vb` und Verweisassemblys aus `Metad1.dll` und `Metad2.dll` erzeugt `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
