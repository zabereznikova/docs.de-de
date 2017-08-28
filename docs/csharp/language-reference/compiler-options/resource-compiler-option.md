---
title: -resource (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /resource
dev_langs:
- CSharp
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fdb7be630300e11c2e63d88bd6add7d229714bfa
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="resource-c-compiler-options"></a>/resource (C#-Compileroptionen)
Bettet die angegebene Ressource in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Die .NET Framework-Ressourcendatei, die in die Ausgabedatei eingebettet werden soll.  
  
 `identifier` (optional)  
 Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird. Der Standardwert ist der Name der Datei.  
  
 `accessibility-modifier` (optional)  
 Barrierefreiheit der Ressource: öffentlich oder privat. Der Standardwert ist „öffentlich“.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), um eine Ressource mit einer Assembly zu verknüpfen, anstatt die Ressourcendatei zur Ausgabedatei hinzuzufügen.  
  
 Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mithilfe des C#-Compilers erstellt werden. Geben Sie `private` als Modifizierer der Barrierefreiheit an. Außer `public` und `private` sind keine anderen Zugriffsmethoden zulässig.  
  
 Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise von [resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=fullName>. Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`*-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.  
  
 **/res** ist die Kurzform von **/resource** (Ressource).  
  
 Die Reihenfolge der Ressourcen in der Ausgabedatei wird durch die in der Befehlszeile angegebene Reihenfolge bestimmt.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Fügen Sie Ihrem Projekt eine Ressourcendatei hinzu.  
  
2.  Wählen Sie im **Projektmappen-Explorer** die Datei aus, die Sie einbetten möchten.  
  
3.  Wählen Sie im Fenster **Eigenschaften** die Option **Buildvorgang** für die Datei aus.  
  
4.  Legen Sie die Option **Buildvorgang** auf **Eingebettete Ressource** fest.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und fügen Sie die Ressourcendatei `rf.resource` an:  
  
```console  
csc /resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

