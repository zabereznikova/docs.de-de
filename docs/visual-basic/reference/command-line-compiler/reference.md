---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: b489a164e56a5e3bdbf7e3cdf24ec330fadedf38
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097552"
---
# <a name="-reference-visual-basic"></a>-reference (Visual Basic)

Hiermit wird bewirkt, dass der Compiler Typinformationen in den angegebenen Assemblys des Projekts zur Verfügung stellt, das Sie aktuell kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-reference:fileList  
```

oder

```console
-r:fileList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileList`|Erforderlich. Durch Trennzeichen getrennte Liste von Assemblydateinamen. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.|  
  
## <a name="remarks"></a>Hinweise  

 Die Dateien, die Sie importieren, müssen Assemblymetadaten enthalten. Nur öffentliche Typen sind außerhalb der Assembly sichtbar. Mit der Option [-addmodule](addmodule.md) werden Metadaten aus einem Modul importiert.  
  
 Wenn Sie auf eine Assembly (Assembly A) verweisen, die selbst auf eine andere Assembly (Assembly B) verweist, müssen Sie auf Assembly B verweisen, wenn:  
  
- Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
- Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.  
  
 Verwenden Sie [-libpath](libpath.md), um das Verzeichnis anzugeben, in dem sich einer oder mehrere der Assemblyverweise befinden.  
  
 Damit der Compiler einen Typ in einer Assembly (nicht in einem Modul) erkennen kann, muss er gezwungen werden, den Typ aufzulösen. Ein Beispiel hierfür ist das Definieren einer Instanz des Typs. Es stehen andere Möglichkeiten zum Auflösen von Typnamen in einer Assembly für den Compiler zur Verfügung. Wenn z. B. von einem Typ in einer Assembly geerbt wird, wird dem Compiler der Typname mitgeteilt.  
  
 Die Vbc.rsp-Antwortdatei, die auf häufig verwendete .NET Framework-Assemblys verweist, wird standardmäßig verwendet. Verwenden Sie `-noconfig`, wenn der Compiler „Vbc.rsp“ nicht verwenden soll.  
  
 Die Kurzform von `-reference` ist `-r`.  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Befehl werden die Quelldatei `Input.vb` und Verweisassemblys aus `Metad1.dll` und `Metad2.dll` kompiliert, um `Out.exe` zu erstellen.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-noconfig](noconfig.md)
- [-target (Visual Basic)](target.md)
- [Public](../../language-reference/modifiers/public.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
