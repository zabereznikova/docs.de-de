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
ms.openlocfilehash: 98c3b8bd809ac550468a5d80e01e6fd16e6d96ea
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924933"
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
 Der Typ der Liste. Muss eine "Bullet" für eine Liste mit Aufzählungszeichen, "Number" für eine nummerierte Liste oder "Table" für eine Tabelle mit zwei Spalten.  
  
 `term`  
 Nur verwendet, wenn `type` ist "table". Ein zu definierender Begriff, die in der Beschreibungstag definiert ist.  
  
 `description`  
 Wenn `type` ist "Bullet" oder "number", `description` ist ein Element in der Liste bei `type` ist "table" `description` ist die Definition der `term`.  
  
## <a name="remarks"></a>Hinweise  
 Die `<listheader>` -Block definiert die Überschrift einer Tabelle oder einer Definition. Wenn Sie eine Tabelle zu definieren, Sie müssen nur ein Eintrag für angegeben `term` in der Überschrift.  
  
 Jedes Element in der Liste wird angegeben, mit einem `<item>` Block. Beim Erstellen einer Definitionsliste müssen Sie angeben, beide `term` und `description`. Allerdings für eine Tabelle, Liste mit Aufzählungszeichen oder nummerierte Liste, Sie müssen nur ein Eintrag für angegeben `description`.  
  
 Eine Liste oder Tabelle lassen sich so viele `<item>` blockiert nach Bedarf.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<list>` Tag, um eine Liste mit Aufzählungszeichen im Abschnitt "Hinweise" definieren.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
