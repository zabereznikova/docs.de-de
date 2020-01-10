---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716635"
---
# <a name="-libpath"></a>-libpath
Gibt den Speicherort der referenzierten Assemblys an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`dirList`|Erforderlich Eine durch Semikolons getrennte Liste von Verzeichnissen, in denen der Compiler suchen soll, wenn eine referenzierte Assembly nicht im aktuellen Arbeitsverzeichnis (dem Verzeichnis, von dem Sie den Compiler aufrufen) oder im System Verzeichnis des Common Language Runtime gefunden wurde. Wenn der Verzeichnisname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-libpath` gibt den Speicherort der Assemblys an, auf die die Option [-Reference verweist](../../../visual-basic/reference/command-line-compiler/reference.md) .  
  
 Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1. Aktuelles Arbeitsverzeichnis Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.  
  
2. Das Verzeichnis des CLR-Systems (Common Language Runtime)  
  
3. Von `-libpath`angegebene Verzeichnisse.  
  
4. Von den LIB-Umgebungsvariablen angegebene Verzeichnisse  
  
 Die `-libpath` Option ist additiv. Wenn Sie den Wert mehrmals angeben, werden alle vorherigen Werte angehängt.  
  
 Verwenden Sie `-reference`, um einen Assemblyverweis anzugeben.  
  
|So legen Sie "-LIBPATH" in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|---|  
|1. Wählen Sie ein Projekt aus, das in **Projektmappen-Explorer**ausgewählt ist. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2. Klicken Sie auf die Registerkarte **Verweise** .<br />3. Klicken Sie auf die Schaltfläche **Verweis Pfade...** .<br />4. Geben Sie im Dialogfeld **Verweis Pfade** den Verzeichnisnamen in das Feld **Ordner:** ein.<br />5. Klicken Sie auf **Ordner hinzufügen**.|  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, um eine exe-Datei zu erstellen. Der Compiler sucht im Arbeitsverzeichnis im Stammverzeichnis des Laufwerks c: und im Verzeichnis neue Assemblys des Laufwerks c: nach Assemblyverweisen.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
