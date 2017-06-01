---
title: Imports-Anweisung (XML-Namespace) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
dev_langs:
- VB
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 546168994973d19336f86f4b4e9ec566f0b9dd91
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="imports-statement-xml-namespace"></a>Imports-Anweisung (XML-Namespace)
Importiert XML-Namespacepräfixe zur Verwendung in XML-Literale und XML-Achseneigenschaften.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Teile  
 `xmlNamespacePrefix`  
 Optional. Die Zeichenfolge, die durch die XML-Elemente und Attribute erhalten `xmlNamespaceName`. Wenn keine `xmlNamespacePrefix` wird angegeben, wird der importierten XML-Namespace der XML-Standardnamespace. Ein gültiger XML-Bezeichner muss sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Erforderlich. Die Zeichenfolge identifiziert den XML-Namespace importiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Imports` -Anweisung können Sie globale XML-Namespaces definieren, mit denen Sie mit XML-Literale und XML-Achseneigenschaften oder als Parameter für die `GetXmlNamespace` Operator. (Informationen zur Verwendung der `Imports` Anweisung zum Importieren eines Alias, die verwendet werden können, in dem Typnamen in Ihrem Code sind finden Sie unter [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespaces mithilfe der `Imports` -Anweisung ist identisch mit der in XML verwendeten Syntax. Daher können Sie eine Namespacedeklaration aus einer XML-Datei kopieren und verwenden Sie es in eine `Imports` Anweisung.  
  
 XML-Namespacepräfixe sind nützlich, wenn Sie wiederholt XML-Elemente erstellen, die aus demselben Namespace möchten. Das XML-Namespacepräfix deklariert, mit der `Imports` Anweisung ist global, in dem Sinne, dass sie für den gesamten Code in der Datei verfügbar ist. Sie können es verwenden, wenn Sie XML-Element-Literalen und beim Zugriff auf XML-Achseneigenschaften erstellen. Weitere Informationen finden Sie unter [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Wenn Sie einen globalen XML-Namespace ohne einen Namespacepräfix definieren (z. B. `Imports <xmlns="http://SomeNameSpace>"`), dieser Namespace als den XML-Standardnamespace angesehen. Für alle XML-Elementliterale oder XML-Attribut-Achseneigenschaften, mit die nicht explizit einen Namespace angegeben werden, wird der XML-Standardnamespace verwendet. Der Standardnamespace wird auch verwendet, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`). Der XML-Standardnamespace gilt nicht, XML-Attributen in XML-Literalen oder XML-Attribut-Achseneigenschaften, mit die nicht mit einen Namespace verfügen.  
  
 XML-Namespaces, die in einem XML-literal definiert sind bezeichnet *lokale XML-Namespaces*, von definierten, XML-Namespaces haben Vorrang vor den `Imports` -Anweisung als global. XML-Namespaces, die durch definiert sind die `Imports` Anweisung haben Vorrang vor XML-Namespaces, die für ein Visual Basic-Projekt importiert. Wenn ein XML-Literal einen XML-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.  
  
 Globale XML-Namespaces folgen denselben Regeln für Bereichs- und Definitionsregeln wie .NET Framework-Namespaces. Sie können daher einschließen einer `Imports` Anweisung, um einen globalen XML-Namespace definieren an können Sie einen .NET Framework-Namespace importieren. Dies schließt sowohl Codedateien und importierten Namespaces auf Projektebene. Informationen über auf Projektebene importierte Namespaces finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, wie z. B. die `Option Strict` -Anweisung, und sie müssen Programmierung Elementdeklarationen, wie z. B. voranstellen `Module` oder `Class` Anweisungen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel importiert eine XML-Standardnamespace und ein XML-Namespace mit dem Präfix identifiziert `ns`. Anschließend erstellt Sie XML-Literale, die beide Namespaces verwenden.  
  
 [!code-vb[VbXMLSamples&#45;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
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
 Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`. Anschließend erstellt Sie ein XML-literal, das das Namespacepräfix verwendet und die abschließende Form des Elements anzeigt.  
  
 [!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Beachten Sie, dass der Compiler das XML-Namespacepräfix aus dem globalen Präfix für die Definition einer standortlokalen Präfix konvertiert.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`. Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples Nr.&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [GetXmlNamespace-Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
