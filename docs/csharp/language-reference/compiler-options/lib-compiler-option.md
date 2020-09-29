---
description: -lib (C#-Compileroptionen)
title: -lib (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 9478501ea98ec1b9d3ec2761bc4ebf3f6bef656c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152441"
---
# <a name="-lib-c-compiler-options"></a>-lib (C#-Compileroptionen)

Die Option **-lib** gibt den Speicherort der Assembly an, auf die verwiesen wird. Dies geschieht mithilfe der Option [-reference (C#-Compileroptionen)](./reference-compiler-option.md).  
  
## <a name="syntax"></a>Syntax  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a>Argumente  

 `dir1`  
 Ein Verzeichnis, in dem der Compiler suchen kann, wenn die Assembly, auf die verwiesen wird, im aktuellen Arbeitsverzeichnis nicht gefunden werden kann (dort wo der Compiler aufgerufen wird) oder im Verzeichnis des CLR-Systems.  
  
 `dir2`  
 Mindestens ein zusätzliches Verzeichnis, in dem nach Assemblyverweisen gesucht werden kann. Trennen Sie zusätzliche Verzeichnisnamen mit einem Komma, aber ohne Leerzeichen zu verwenden.  
  
## <a name="remarks"></a>Bemerkungen  

 Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1. Aktuelles Arbeitsverzeichnis Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.  
  
2. Das Verzeichnis des CLR-Systems (Common Language Runtime)  
  
3. Von **-lib** angegebene Verzeichnisse  
  
4. Von den LIB-Umgebungsvariablen angegebene Verzeichnisse  
  
 Verwenden Sie **-reference**, um einen Assemblyverweis anzugeben.  
  
 **-lib** ist additiv. Wenn es mehr als einmal angegeben wird, wird es an jeden vorherigen Wert angehängt.  
  
 Alternativ zu **-lib** können Sie auch alle erforderlichen Assemblys direkt in das Arbeitsverzeichnis kopieren. Dadurch können Sie den Namen der Assembly ganz einfach an **-reference** übergeben. Anschließend können Sie die Assemblys wieder aus dem Arbeitsverzeichnis löschen. Da der Pfad der abhängigen Assembly nicht im Assemblymanifest angegeben ist, kann die Anwendung auf dem Zielcomputer gestartet werden. Sie findet und verwendet die Assembly dann im globalen Assemblycache.  
  
 Nur weil der Compiler auf die Assembly verweisen kann, heißt das nicht, dass die CLR die Assembly zur Laufzeit finden und laden kann. Weitere Informationen dazu, wie die Laufzeit nach verwiesenen Assemblys sucht, finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Verweispfad**.  
  
3. Modifizieren Sie den Inhalt des Listenfelds.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## <a name="example"></a>Beispiel  

 Kompilieren Sie „t2.cs“, um eine EXE-Datei zu erstellen. Der Compiler sucht im Arbeitsverzeichnis und im Stammverzeichnis des Laufwerks C nach Assemblyverweisen.  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
