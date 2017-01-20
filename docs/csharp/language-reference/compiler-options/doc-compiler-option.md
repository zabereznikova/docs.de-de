---
title: "/doc (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FileProperties.BuildAction"
  - "/doc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "comments, C# code"
  - "XML documentation [C#], comments in source files"
  - "doc compiler option [C#]"
  - "Visual C#, XML documentation for"
  - "-doc compiler option [C#]"
  - "/doc compiler option [C#]"
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /doc (C# Compiler Options)
Mit der Option **\/doc** können Sie Dokumentationskommentare in eine XML\-Datei einfügen.  
  
## Syntax  
  
```  
/doc:file  
```  
  
## Argumente  
 `file`  
 die Ausgabedatei für XML, in die die Kommentare der Quellcodedateien der Kompilierung eingetragen werden.  
  
## Hinweise  
 Dokumentationskommentare, die in Quellcodedateien folgenden Typen bzw. Membern vorangestellt sind, können verarbeitet und der XML\-Datei hinzugefügt werden:  
  
-   Benutzerdefinierten Typen wie [class](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md) oder [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   Membern wie Feldern, [Ereignissen](../../../csharp/language-reference/keywords/event.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md) oder Methoden  
  
 Die Quellcodedatei, die **Main** enthält, wird zuerst in die XML ausgegeben.  
  
 Um die generierte XML\-Datei mit dem [IntelliSense](/visual-studio/ide/using-intellisense)\-Feature zu verwenden, benennen Sie die XML\-Datei nach der Assembly, die unterstützt werden soll, und stellen anschließend sicher, dass sich XML\-Datei und Assembly im selben Verzeichnis befinden.  Wenn dann im Visual Studio\-Projekt auf die Assembly verwiesen wird, wird die XML\-Datei auch gefunden.  Weitere Informationen finden Sie unter [Anzeigen von Codekommentaren](/visual-studio/ide/supplying-xml-code-comments).  
  
 Sofern, dass Sie mit [\/target: Modul](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, enthält \<die\>\<`file` \/Assemblytags \> Assembly, die den Namen der Datei angeben, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
> [!NOTE]
>  Die Option \/doc gilt für alle Eingabedateien. Wenn dies in den Projekteinstellungen festgelegt wurde, gilt diese Option für alle Dateien im Projekt.  Warnungen zu Dokumentationskommentaren für eine bestimmte Datei oder einen bestimmten Codeabschnitt können Sie deaktivieren, indem Sie [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) verwenden.  
  
 Informationen über Möglichkeiten zum Erstellen von Dokumentationen anhand von Codekommentaren finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Registerkarte **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **XML\-Dokumentationsdatei**.  
  
 Informationen darüber, wie Sie diese Compileroption programmgesteuert festlegen können, finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)