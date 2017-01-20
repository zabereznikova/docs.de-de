---
title: "&lt;permission&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<permission> XML tag"
  - "permission XML tag"
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;permission&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt eine erforderliche Berechtigung für den Member an.  
  
## Syntax  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übersetzt `member` in den in der XML\-Ausgabe enthaltenen kanonischen Elementnamen.  Schließen Sie `member` in Anführungszeichen \(" "\) ein.  
  
 `description`  
 Eine Beschreibung des Zugriffs auf den Member.  
  
## Hinweise  
 Verwenden Sie das `<permission>`\-Tag, um den Zugriff eines Members zu dokumentieren.  Verwenden Sie die <xref:System.Security.PermissionSet>\-Klasse, um den Zugriff auf einen Member anzugeben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mithilfe des `<permission>`\-Tags beschrieben, dass <xref:System.Security.Permissions.FileIOPermission> von der `ReadFile`\-Methode benötigt wird.  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)