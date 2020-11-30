---
description: -resource (C#-Compileroptionen)
title: -resource (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193776"
---
# <a name="-resource-c-compiler-options"></a>-resource (C#-Compileroptionen)

Bettet die angegebene Ressource in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumente  

 `filename`  
 Die .NET-Ressourcendatei, die in die Ausgabedatei eingebettet werden soll  
  
 `identifier` (optional)  
 Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird. Der Standardwert ist der Name der Datei.  
  
 `accessibility-modifier` (optional)  
 Barrierefreiheit der Ressource: öffentlich oder privat. Der Standardwert ist public.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie [-linkresource](./linkresource-compiler-option.md), um eine Ressource mit einer Assembly zu verknüpfen, anstatt die Ressourcendatei zur Ausgabedatei hinzuzufügen.  
  
 Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mithilfe des C#-Compilers erstellt werden. Geben Sie `private` als Modifizierer der Barrierefreiheit an. Außer `public` und `private` sind keine anderen Zugriffsmethoden zulässig.  
  
 Wenn es sich bei `filename` um eine .NET-Ressourcendatei handelt, die beispielsweise von [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.  
  
 **-res** ist die Kurzform von **-resource**.  
  
 Die Reihenfolge der Ressourcen in der Ausgabedatei wird durch die in der Befehlszeile angegebene Reihenfolge bestimmt.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Fügen Sie Ihrem Projekt eine Ressourcendatei hinzu.  
  
2. Wählen Sie im **Projektmappen-Explorer** die Datei aus, die Sie einbetten möchten.  
  
3. Wählen Sie im Fenster **Eigenschaften** die Option **Buildvorgang** für die Datei aus.  
  
4. Legen Sie die Option **Buildvorgang** auf **Eingebettete Ressource** fest.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Beispiel  

 Kompilieren Sie `in.cs`, und fügen Sie die Ressourcendatei `rf.resource` an:  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
