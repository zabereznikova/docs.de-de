---
title: "&lt;list&gt; (Visual Basic) | Microsoft Docs"
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
  - "listheader XML tag"
  - "<item> XML tag"
  - "<list> XML tag"
  - "<listheader> XML tag"
  - "term XML tag"
  - "list XML tag"
  - "<description> XML tag"
  - "description XML tag"
  - "item XML tag"
  - "<term> XML tag"
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;list&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Definiert eine Liste oder Tabelle.  
  
## Syntax  
  
```  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Parameter  
 `type`  
 Der Typ der Liste.  Muss bei Aufzählungen "bullet" sein, "number" bei nummerierten Listen und "table" bei zweispaltigen Tabellen.  
  
 `term`  
 Nur verwendet, wenn `type` den Wert "table" hat. Ein zu definierender Begriff, der im Beschreibungstag definiert wird.  
  
 `description`  
 Wenn `type` den Wert "bullet" oder "number" hat, ist `description` ein Element in der Liste. Wenn `type` den Wert "table" hat, ist `description` die Definition von `term`.  
  
## Hinweise  
 Der `<listheader>`\-Block wird zur Definition der Überschrift einer Tabelle oder einer Definitionsliste verwendet.  Beim Definieren einer Tabelle muss in der Überschrift lediglich ein Eintrag für `term` angegeben werden.  
  
 Jedes Element der Liste wird mit einem `<item>`\-Block angegeben.  Wenn Sie eine Definitionsliste erstellen, müssen Sie sowohl `term` als auch `description` angeben.  Für eine Tabelle, eine Aufzählung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.  
  
 Eine Liste oder Tabelle kann beliebig viele `<item>`\-Blöcke enthalten.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem `<list>`\-Tag im Hinweisabschnitt eine Aufzählung definiert.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)