---
title: Imports-Anweisung (XML-Namespace)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: ba7475416d8a4e2eb3c892d457c03eeb695045eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imports-statement-xml-namespace"></a>Imports-Anweisung (XML-Namespace)
Importiert die XML-Namespacepräfixe zur Verwendung in XML-Literale und XML-Achseneigenschaften.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Teile  
 `xmlNamespacePrefix`  
 Dies ist optional. Die Zeichenfolge, die durch die XML-Elemente und Attribute verweisen auf `xmlNamespaceName`. Wenn kein `xmlNamespacePrefix` wird angegeben, wird der importierten XML-Namespace der XML-Standardnamespace. Ein gültiger XML-Bezeichner muss sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Erforderlich. Die Zeichenfolge identifiziert den XML-Namespace importiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Können Sie die `Imports` Anweisung, um globale XML-Namespaces definieren, die Sie verwenden können, mit XML-Literale und XML-Achseneigenschaften oder als Parameter für die `GetXmlNamespace` Operator. (Informationen zum Verwenden der `Imports` Anweisung, um einen Alias zu importieren, die verwenden können, in dem Typnamen in Ihrem Code verwendet werden finden Sie unter [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespaces mithilfe der `Imports` -Anweisung ist identisch mit der Syntax, die im XML-Format verwendet. Aus diesem Grund können Sie eine Namespacedeklaration aus einer XML-Datei kopieren und verwenden Sie ihn in ein `Imports` Anweisung.  
  
 XML-Namespacepräfixe sind nützlich, wenn wiederholte XML-Elemente erstellen, die aus dem gleichen Namespace werden sollen. Das XML-Namespacepräfix deklariert, mit der `Imports` Anweisung ist global, in dem Sinne, dass er für den gesamten Code in der Datei verfügbar ist. Sie können beim Erstellen von XML-Elementliteralen und beim Zugriff auf XML-Achseneigenschaften. Weitere Informationen finden Sie unter [XML-Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Wenn Sie einen globalen XML-Namespace, ohne ein Namespacepräfix definieren (z. B. `Imports <xmlns="http://SomeNameSpace>"`), diesen Namespace gilt die XML-Standardnamespace. Der XML-Standardnamespace wird verwendet, für alle XML-Elementliteralen oder XML-Achse Attributeigenschaften, die nicht explizit einen Namespace angeben. Der Standardnamespace wird auch verwendet, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`). Der XML-Standardnamespace gilt nicht für XML-Attribute in XML-Literalen oder XML-Achse Attributeigenschaften, die nicht mit einen Namespace verfügen.  
  
 XML-Namespaces, die in einem XML-literal definiert sind, die bezeichnet werden *lokale XML-Namespaces*, durch definierten, XML-Namespaces haben Vorrang vor den `Imports` -Anweisung als global. XML-Namespaces, die von definiert sind die `Imports` Anweisung haben Vorrang vor XML-Namespaces, die für ein Visual Basic-Projekt importiert. Wenn ein XML-Literal einen XML-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.  
  
 Globale XML-Namespaces, gelten dieselben Regeln für Definition von Ansichtsbereichen und Definition als .NET Framework-Namespaces. Sie können daher einschließen einer `Imports` Anweisung, um einen globalen XML-Namespace definieren an einer beliebigen Stelle können Sie einen .NET Framework-Namespace importieren. Dies schließt Codedateien und importierten Namespaces auf Projektebene. Weitere Informationen zu importierten Namespaces auf Projektebene finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Jeder Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Programmierung Elementdeklarationen, z. B. `Module` oder `Class` Anweisungen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel importiert eine XML-Standardnamespace und einen XML-Namespace identifiziert, mit dem Präfix `ns`. Anschließend erstellt es XML-Literale, die beide Namespaces verwenden.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`. Anschließend wird ein XML-literal, das das Namespacepräfix verwendet und zeigt die endgültige Form des Elements erstellt.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Beachten Sie, dass der Compiler das XML-Namespacepräfix aus einem globalen Präfix für die Präfixdefinition eines lokalen konvertiert.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`. Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [GetXmlNamespace-Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
