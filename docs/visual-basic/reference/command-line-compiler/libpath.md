---
title: / LIBPATH | Microsoft-Dokumentation
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
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
ms.openlocfilehash: cc534e782cff34f0c4882f3da2af973fed69ff80
ms.lasthandoff: 03/13/2017

---
# <a name="libpath"></a>/libpath
Gibt den Speicherort der Assemblys verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`dirList`|Erforderlich. Durch Semikolons getrennte Liste von Verzeichnissen, die der Compiler sucht, wenn eine Assembly nicht befindet sich entweder in das aktuelle Arbeitsverzeichnis (dem Verzeichnis, aus dem Sie den Compiler starten) oder die common Language Runtime-Systemverzeichnis. Wenn der Verzeichnisname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `/libpath` Option gibt den Speicherort der Assemblys, auf die verwiesen wird die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) Option.  
  
 Der Compiler sucht nach Assemblyverweisen, die nicht voll in der folgenden Reihenfolge qualifiziert werden:  
  
1.  Aktuelles Arbeitsverzeichnis. Dies ist das Verzeichnis, in dem der Compiler aufgerufen wird.  
  
2.  Die common Language Runtime-Systemverzeichnis.  
  
3.  Verzeichnisse, die durch angegebene `/libpath`.  
  
4.  Durch die LIB-Umgebungsvariablen angegebenen Verzeichnisse.  
  
 Die `/libpath` -Option ist additiv; Angabe es mehr als einmal an die vorherigen Werte angehängt.  
  
 Verwendung `/reference` um einen Assemblyverweis anzugeben.  
  
|Zum Festlegen von/LIBPATH in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Verweise** Registerkarte.<br />3.  Klicken Sie auf die **Verweispfade... ** Schaltfläche.<br />4.  In der **Verweispfade** Dialogfeld Geben Sie den Namen des Verzeichnisses, in dem **Ordner:** Feld.<br />5.  Klicken Sie auf **Ordner hinzufügen**.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` .exe-Datei zu erstellen. Der Compiler sucht im Arbeitsverzeichnis, im Stammverzeichnis von Laufwerk C: und im Verzeichnis New Assemblies von Laufwerk C: für Assemblyverweise.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
