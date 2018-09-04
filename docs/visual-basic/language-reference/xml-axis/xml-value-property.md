---
title: XML-Value-Eigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 2b0719320db5843d5d010bfbd70e551646e3ded9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533390"
---
# <a name="xml-value-property-visual-basic"></a>XML-Value-Eigenschaft (Visual Basic)
Ermöglicht den Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein `String` , den Wert des ersten Elements der Auflistung enthält oder `Nothing` , wenn die Auflistung leer ist.  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft erleichtert das Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Diese Eigenschaft überprüft zuerst, ob die Auflistung über mindestens ein Objekt enthält. Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing`. Andernfalls gibt diese Eigenschaft den Wert der die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft des ersten Elements in der Auflistung.  
  
> [!NOTE]
>  Beim Zugriff auf den Wert eines XML-Attributs mithilfe der "\@'-ID, den Wert des Attributs wird als zurückgegeben eine `String` und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.  
  
 Um andere Elemente in einer Auflistung zuzugreifen, können Sie die Indexereigenschaft für XML-Erweiterung verwenden. Weitere Informationen finden Sie unter [Erweiterungsindexereigenschaft](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Vererbung  
 Die meisten Benutzer haben keinen implementieren <xref:System.Collections.Generic.IEnumerable%601>, und können daher diesen Abschnitt ignorieren.  
  
 Die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft ist eine Erweiterungseigenschaft für Typen, implementieren `IEnumerable(Of XElement)`. Die Bindung dieser Eigenschaft für die Erweiterung wird wie die Bindung der Erweiterungsmethoden: Wenn ein Typ eine der Schnittstellen implementiert und definiert eine Eigenschaft mit dem Namen "Value", hat diese Eigenschaft Vorrang vor der Erweiterungseigenschaft. Das heißt, diese <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft kann überschrieben werden, definieren Sie eine neue Eigenschaft in einer Klasse, die implementiert `IEnumerable(Of XElement)`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft auf den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Im Beispiel wird die untergeordneten Achseneigenschaft verwendet, um die Auflistung aller untergeordneten Knoten mit dem Namen abzurufen `phone` , die sich in der `contact` Objekt.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie den Wert eines XML-Attributs aus einer Auflistung von abrufen <xref:System.Xml.Linq.XAttribute> Objekte. Im Beispiel wird die Attributachseneigenschaft verwendet, um den Wert der an die `type` -Attribut für alle von der `phone` Elemente.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Erweiterungsindexereigenschaft](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [Untergeordnete XML-Achseneigenschaft](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [XML-Attributachseneigenschaft](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
