---
description: -doc (C#-Compileroptionen)
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
ms.openlocfilehash: e55b86e5b028fb871f309d80217477cfd164c106
ms.sourcegitcommit: f0eb7eeedf3ceec726499fa678786d03083214ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "98629253"
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
  
## <a name="remarks"></a>Bemerkungen  

 In Quellcodedateien können Dokumentationskommentare, die Folgendem vorausgehen, verarbeitet und der XML-Datei hinzugefügt werden:  
  
- Benutzerdefinierte Typen wie eine [Klasse](../keywords/class.md), ein [Delegat](../builtin-types/reference-types.md#the-delegate-type), oder eine [Schnittstelle](../keywords/interface.md)  
  
- Member wie ein Feld, ein [Ereignis](../keywords/event.md), eine [Eigenschaft](../../programming-guide/classes-and-structs/using-properties.md), oder eine Methode  
  
 Die Quellcodedatei, die Main enthält, wird zuerst in XML ausgegeben.  
  
 Lassen Sie den Dateinamen der XML-Datei mit der Assembly, die Sie unterstützen möchten, identisch sein, und stellen Sie sicher, dass sich die XML-Datei im gleichen Verzeichnis wie die Assembly befindet, um die generierte XML-Datei für die Verwendung mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktion zu verwenden. Demnach wird auch die XML-Datei gefunden, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird. Weitere Informationen finden Sie unter [Anzeigen von XML-Codekommentaren](/visualstudio/ide/reference/generate-xml-documentation-comments).  
  
 Wenn Sie nicht mit [-target:module](./target-module-compiler-option.md) kompilieren, enthält `file` die Tags \<assembly>\</assembly>, die den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung angeben.  
  
> [!NOTE]
> Die Option „-doc“ gilt für alle Eingabedateien; oder, wenn sie in den Projekteinstellungen festgelegt wurde, für alle Dateien im Projekt. Verwenden Sie zum Deaktivieren von Warnungen im Zusammenhang mit Dokumentationskommentare für eine bestimmte Datei oder einen Codeabschnitt [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Weitere Informationen für Methoden zum Generieren von Dokumentation aus Kommentaren in Ihrem Code finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-2019-development-environment"></a>So legen Sie diese Compileroption in der Entwicklungsumgebung für Visual Studio 2019 fest  

1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
2. Klicken Sie auf die Registerkarte **Erstellen**.
3. Ändern Sie die Eigenschaft der **XML-Dokumentationsdatei**.
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-for-mac-development-environment"></a>So legen Sie diese Compileroption in der Entwicklungsumgebung für Visual Studio für Mac fest  
  
1. Öffnen Sie die Seite **Optionen** des Projekts.
2. Wählen Sie die Registerkarte **Compiler** aus.
3. Wählen Sie **XML-Dokumentation generieren** aus, und geben Sie den Dateinamen in das Textfeld ein.

Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
