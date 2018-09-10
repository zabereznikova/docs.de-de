---
title: -recurse (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 1fc5591cb73164e15384eb4407a6e61e903eedbb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529896"
---
# <a name="-recurse-c-compiler-options"></a>-recurse (C#-Compileroptionen)
Mit der Option „-recurse“ können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (dir) oder des Projektverzeichnisses kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir` (optional)  
 Das Verzeichnis, in dem die Suche beginnen soll. Wenn dieses nicht angegeben wird, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Mit der Option **-recurse** können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (`dir`) oder des Projektverzeichnisses kompilieren.  
  
 Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne **-recurse** zu verwenden.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="example"></a>Beispiel  
 Kompiliert alle C#-Dateien im aktuellen Verzeichnis:  
  
```console  
csc *.cs  
```  
  
 Kompiliert alle C#-Dateien im Verzeichnis „dir1\dir2“ sowie in allen Verzeichnisse darunter und generiert „dir2.dll“:  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
