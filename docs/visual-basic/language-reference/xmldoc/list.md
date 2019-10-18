---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524750"
---
# <a name="list-visual-basic"></a>\<list > (Visual Basic)
Definiert eine Liste oder Tabelle.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
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
  
## <a name="parameters"></a>Parameter  
 `type`  
 Der Typ der Liste. Muss ein "Aufzählungs Zeichen" für eine Aufzählungs Liste, "Zahl" für eine nummerierte Liste oder "Table" für eine Tabelle mit zwei Spalten sein.  
  
 `term`  
 Wird nur verwendet, wenn `type` "Table" ist. Ein zu definierenden Begriff, der im Beschreibungs-Tag definiert ist.  
  
 `description`  
 Wenn `type` "Bullet" oder "Number" ist, ist `description` ein Element in der Liste, wenn `type` "Table" ist. `description` ist die Definition des `term`.  
  
## <a name="remarks"></a>Hinweise  
 Der `<listheader>`-Block definiert die Überschrift einer Tabelle oder einer Definitionsliste. Wenn Sie eine Tabelle definieren, müssen Sie in der Überschrift nur einen Eintrag für `term` bereitstellen.  
  
 Jedes Element in der Liste wird mit einem `<item>`-Block angegeben. Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben. Für eine Tabelle, eine aufzählige Liste oder eine nummerierte Liste müssen Sie jedoch nur einen Eintrag für `description` bereitstellen.  
  
 Eine Liste oder Tabelle kann beliebig viele `<item>` Blöcke enthalten.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<list>`-Tag zum Definieren einer aufzurufenden Liste im Abschnitt "Hinweise" verwendet.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
