---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234071d043b2649e2438ed20fe044fb89cdb9bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655888"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Gibt den Namen der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`filename`|Erforderlich. Der Name der Ausgabedatei, die der Compiler erstellt. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie den vollständigen Namen und die Erweiterung der zu erstellenden Datei. Wenn Sie nicht der Fall ist, akzeptiert die .exe-Datei seinen Namen aus der Quellcode Datei mit den `Sub Main` Prozedur und die DLL-Datei den Namen aus der ersten Quellcodedatei dauert.  
  
 Wenn Sie einen Dateinamen ohne Erweiterung .exe oder .dll angeben, der Compiler automatisch fügt die Erweiterung für Sie, abhängig von der angegebene Wert für die `-target` -Compileroption.  
  
|Festzulegende - Timeout in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert in der **Assemblyname** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und erstellt die Ausgabedatei `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-Ziel (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
