---
title: Imports-Anweisung - XML-Namespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 1100afd89b27e789c0db713291ed3656092fb0c7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43802391"
---
# <a name="imports-statement-xml-namespace"></a>Imports-Anweisung (XML-Namespace)
Importiert die XML-Namespacepräfixe für XML-Literale und XML-Achseneigenschaften.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Teile  
 `xmlNamespacePrefix`  
 Dies ist optional. Die Zeichenfolge, die durch die XML-Elemente und Attribute verweisen auf `xmlNamespaceName`. Wenn kein `xmlNamespacePrefix` wird angegeben, wird der importierte XML-Namespace der XML-Standardnamespace. Ein gültiger XML-Bezeichner muss sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Erforderlich. Die Zeichenfolge, die Identifizieren des XML-Namespace importiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Können Sie die `Imports` Anweisung, um globale XML-Namespaces definieren, mit denen Sie mit XML-Literale und XML-Achseneigenschaften oder als Parameter übergeben, um die `GetXmlNamespace` Operator. (Informationen zur Verwendung der `Imports` Anweisung, um einen Alias zu importieren, die, in dem Typnamen verwendet werden, in Ihrem Code verwendet werden können, finden Sie unter [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespaces mithilfe der `Imports` -Anweisung ist identisch mit der Syntax, die im XML-Format verwendet. Aus diesem Grund können Sie eine Namespacedeklaration aus einer XML-Datei kopieren und verwenden Sie ihn in ein `Imports` Anweisung.  
  
 XML-Namespacepräfixe sind nützlich, wenn Sie wiederholt auf XML-Elemente erstellen, die aus dem gleichen Namespace sind möchten. Das XML-Namespacepräfix deklariert, mit der `Imports` Anweisung ist global, in dem Sinne, dass sie auf den gesamten Code in der Datei verfügbar ist. Sie können es verwenden, wenn Sie XML-Elementliteralen und beim Zugriff auf XML-Achseneigenschaften erstellen. Weitere Informationen finden Sie unter [XML-Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md).  
  
 Wenn Sie einen globalen XML-Namespace ohne ein Namespacepräfix zu definieren (z. B. `Imports <xmlns="http://SomeNameSpace>"`), diesen Namespace gilt den XML-Standardnamespace. Der XML-Standardnamespace wird verwendet, für alle XML-Elementliteralen oder XML-Attribut-Achseneigenschaften, die nicht explizit einen Namespace angeben. Der Standardnamespace wird auch verwendet werden, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`). Der XML-Standardnamespace gilt nicht, um XML-Attribute im XML-Literalen oder XML-Attribut-Achseneigenschaften, die nicht mit einen Namespace verfügen.  
  
 XML-Namespaces, die in einem XML-literal definiert werden die aufgerufen werden, *lokale XML-Namespaces*, haben Vorrang vor XML-Namespaces, die von definiert sind die `Imports` -Anweisung als global. XML-Namespaces, die von definiert sind die `Imports` Anweisung haben Vorrang vor XML-Namespaces, die für ein Visual Basic-Projekt importiert. Wenn ein XML-Literal einen XML-Namespace definiert ist, gilt dieses lokale Namespace nicht für eingebettete Ausdrücke.  
  
 Globale XML-Namespaces, gelten dieselben Regeln einschränken und die Definition als .NET Framework-Namespaces. Sie können daher einschließen einer `Imports` Anweisung, um einen globalen XML-Namespace definieren an einer beliebigen Stelle auf der Sie einen .NET Framework-Namespace importieren können. Dies schließt sowohl Codedateien und importierten Namespaces auf Projektebene. Weitere Informationen zu importierten Namespaces auf Projektebene, finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Programmierung Elementdeklarationen, z. B. `Module` oder `Class` Anweisungen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel importiert eine XML-Standardnamespace und ein XML-Namespace identifiziert, mit dem Präfix `ns`. Anschließend erstellt es ein XML-Literale, die beide Namespaces verwenden.  
  
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
 Das folgende Beispiel importiert die XML-Namespacepräfix `ns`. Anschließend erstellt es ein XML-literal, das das Namespacepräfix verwendet, und zeigt die endgültige Form des Elements an.  
  
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
  
 Beachten Sie, dass der Compiler das XML-Namespacepräfix über ein globales Präfix in eine lokale Präfixdefinition konvertiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel importiert die XML-Namespacepräfix `ns`. Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)  
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [GetXmlNamespace-Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
