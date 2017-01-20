---
title: "&lt;param&gt; (Visual Basic) | Microsoft Docs"
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
  - "param XML tag"
  - "<param> XML tag"
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;param&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Definiert einen Parameternamen und eine Parameterbeschreibung.  
  
## Syntax  
  
```  
<param name="name">description</param>  
```  
  
#### Parameter  
 `name`  
 der Name des Methodenparameters.  Der Name muss in doppelte Anführungszeichen \(**" "**\) eingeschlossen werden.  
  
 `description`  
 eine Beschreibung für den Parameter.  
  
## Hinweise  
 Das `<param>`\-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter der Methode zu beschreiben.  
  
 Der Text für das `<param>`\-Tag wird in den folgenden Links:  
  
-   Parameterinformationen von IntelliSense.  Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visual-studio/ide/using-intellisense).  
  
-   Objektkatalog.  Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird das `<param>`\-Tag zur Beschreibung des `id`\-Parameters verwendet.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)