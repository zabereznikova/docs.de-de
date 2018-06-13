---
title: -doc (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: ac1275285a8ba403297e51438fbf0d47d811ca61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216147"
---
# <a name="-doc-c-compiler-options"></a>-doc (C#-Compileroptionen)
Mit der Option **-doc** können Sie Dokumentationskommentare in eine XML-Datei einfügen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Die Ausgabedatei für XML, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird.  
  
## <a name="remarks"></a>Hinweise  
 In Quellcodedateien können Dokumentationskommentare, die Folgendem vorausgehen, verarbeitet und der XML-Datei hinzugefügt werden:  
  
-   Benutzerdefinierte Typen wie eine [Klasse](../../../csharp/language-reference/keywords/class.md), ein [Delegat](../../../csharp/language-reference/keywords/delegate.md), oder eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md)  
  
-   Member wie ein Feld, ein [Ereignis](../../../csharp/language-reference/keywords/event.md), eine [Eigenschaft](../../../csharp/programming-guide/classes-and-structs/using-properties.md), oder eine Methode  
  
 Die Quellcodedatei, die Main enthält, wird zuerst in XML ausgegeben.  
  
 Lassen Sie den Dateinamen der XML-Datei mit der Assembly, die Sie unterstützen möchten, identisch sein, und stellen Sie sicher, dass sich die XML-Datei im gleichen Verzeichnis wie die Assembly befindet, um die generierte XML-Datei für die Verwendung mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktion zu verwenden. Demnach wird auch die XML-Datei gefunden, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird. Weitere Informationen finden Sie unter [Anzeigen von XML-Codekommentaren](/visualstudio/ide/supplying-xml-code-comments).  
  
 Wenn Sie nicht mit [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, enthält `file` die Tags \<assembly>\</assembly>, die den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung angeben.  
  
> [!NOTE]
>  Die Option „-doc“ gilt für alle Eingabedateien; oder, wenn sie in den Projekteinstellungen festgelegt wurde, für alle Dateien im Projekt. Verwenden Sie zum Deaktivieren von Warnungen im Zusammenhang mit Dokumentationskommentare für eine bestimmte Datei oder einen Codeabschnitt [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Weitere Informationen für Methoden zum Generieren von Dokumentation aus Kommentaren in Ihrem Code finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**-Seite des Projekts.  
  
2.  Klicken Sie auf die Registerkarte **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft der **XML-Dokumentationsdatei**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
