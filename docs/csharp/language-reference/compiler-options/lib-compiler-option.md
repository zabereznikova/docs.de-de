---
title: -lib (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /lib
dev_langs:
- CSharp
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 27bcca456a7a5c884c33de6429e06c94afc9536a
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="lib-c-compiler-options"></a>/lib (C#-Compileroptionen)
Die Option **/lib** gibt den Speicherort der Assembly an, auf die verwiesen wird. Dies geschieht mithilfe der Option [/reference (C# Compiler Options)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
## <a name="syntax"></a>Syntax  
  
```console  
/lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a>Argumente  
 `dir1`  
 Ein Verzeichnis, in dem der Compiler suchen kann, wenn die Assembly, auf die verwiesen wird, im aktuellen Arbeitsverzeichnis nicht gefunden werden kann (dort wo der Compiler aufgerufen wird) oder im Verzeichnis des CLR-Systems.  
  
 `dir2`  
 Mindestens ein zusätzliches Verzeichnis, in dem nach Assemblyverweisen gesucht werden kann. Trennen Sie zusätzliche Verzeichnisnamen mit einem Komma, aber ohne Leerzeichen zu verwenden.  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1.  Aktuelles Arbeitsverzeichnis Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.  
  
2.  Das Verzeichnis des CLR-Systems (Common Language Runtime)  
  
3.  Von **/lib** angegebene Verzeichnisse  
  
4.  Von den LIB-Umgebungsvariablen angegebene Verzeichnisse  
  
 Verwenden Sie **/reference**, um einen Assemblyverweis anzugeben.  
  
 **/lib** ist additiv. Wenn es mehr als einmal angegeben wird, wird es an jeden vorherigen Wert angehängt.  
  
 Alternativ zu **/lib** können Sie auch alle erforderlichen Assemblys direkt in das Arbeitsverzeichnis kopieren. Damit können Sie den Namen das Assembly ganz einfach an **/reference** übergeben. Anschließend können Sie die Assemblys wieder aus dem Arbeitsverzeichnis löschen. Da der Pfad der abhängigen Assembly nicht im Assemblymanifest angegeben ist, kann die Anwendung auf dem Zielcomputer gestartet werden. Sie findet und verwendet die Assembly dann im globalen Assemblycache.  
  
 Nur weil der Compiler auf die Assembly verweisen kann, heißt das nicht, dass die CLR die Assembly zur Laufzeit finden und laden kann. Weitere Informationen dazu, wie die Laufzeit nach verwiesenen Assemblys sucht, finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Verweispfad**.  
  
3.  Modifizieren Sie den Inhalt des Listenfelds.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie „t2.cs“, um eine EXE-Datei zu erstellen. Der Compiler sucht im Arbeitsverzeichnis und im Stammverzeichnis des Laufwerks C nach Assemblyverweisen.  
  
```console  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB: Vorgehensweise: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
