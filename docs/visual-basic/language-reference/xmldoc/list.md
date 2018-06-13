---
title: '&lt;Liste&gt; (Visual Basic)'
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
ms.openlocfilehash: f03924217393e1e909b086b282f1c62ddb471522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603612"
---
# <a name="ltlistgt-visual-basic"></a>&lt;Liste&gt; (Visual Basic)
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
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Der Typ der Liste. Muss eine "Bullet" für eine Liste mit Aufzählungszeichen, "Number" für eine nummerierte Liste oder "Table" für eine zweispaltige Tabelle.  
  
 `term`  
 Nur verwendet, wenn `type` ist "table". Ein Ausdruck zum definieren, die in der Beschreibungstag definiert ist.  
  
 `description`  
 Wenn `type` ist "Bullet" oder "number" `description` ist ein Element in der Liste beim `type` ist "table" `description` ist die Definition der `term`.  
  
## <a name="remarks"></a>Hinweise  
 Die `<listheader>` -Block definiert die Überschrift einer Tabelle oder die Definition. Wenn Sie eine Tabelle zu definieren, Sie müssen nur ein Eintrag für angegeben `term` in der Überschrift.  
  
 Jedes Element in der Liste wird angegeben, mit einer `<item>` Block. Wenn Sie eine Definitionsliste zu erstellen, müssen Sie beide angeben `term` und `description`. Allerdings für eine Tabelle, eine Liste mit Aufzählungszeichen oder eine nummerierte Liste, Sie müssen nur ein Eintrag für angegeben `description`.  
  
 Eine Liste oder Tabelle können beliebig viele `<item>` blockiert nach Bedarf.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<list>` -Tag, um eine Liste mit Aufzählungszeichen im Abschnitt "Hinweise" definieren.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
