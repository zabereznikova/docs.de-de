---
title: -recurse (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b50454112bc7aee6c3e0f8fe674e8727ca9e49be
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
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
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
