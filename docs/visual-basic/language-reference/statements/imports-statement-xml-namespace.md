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
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404536"
---
# <a name="imports-statement-xml-namespace"></a>Imports-Anweisung (XML-Namespace)

Importiert XML-Namespace Präfixe zur Verwendung in XML-Literalen und XML-Achsen Eigenschaften.

## <a name="syntax"></a>Syntax

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>Bestandteile

`xmlNamespacePrefix`  
Optional. Die Zeichenfolge, auf die XML-Elemente und-Attribute verweisen können `xmlNamespaceName` . Wenn kein `xmlNamespacePrefix` angegeben wird, ist der importierte XML-Namespace der Standard-XML-Namespace. Muss ein gültiger XML-Bezeichner sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).

`xmlNamespaceName`  
Erforderlich. Die Zeichenfolge, die den importierten XML-Namespace identifiziert.

## <a name="remarks"></a>Bemerkungen

Sie können die- `Imports` Anweisung verwenden, um globale XML-Namespaces zu definieren, die Sie mit XML-Literalen und XML-Achsen Eigenschaften verwenden können, oder als Parameter, die an den Operator weitergegeben werden `GetXmlNamespace` . (Informationen zum Verwenden der- `Imports` Anweisung zum Importieren eines Alias, der verwendet werden kann, wo Typnamen in Ihrem Code verwendet werden, finden Sie unter [Imports-Anweisung (.NET-Namespace und-Typ)](imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespace mit der- `Imports` Anweisung ist identisch mit der Syntax, die in XML verwendet wird. Daher können Sie eine Namespace Deklaration aus einer XML-Datei kopieren und in einer- `Imports` Anweisung verwenden.

XML-Namespace Präfixe sind nützlich, wenn Sie wiederholt XML-Elemente aus demselben Namespace erstellen möchten. Das mit der-Anweisung deklarierte XML-Namespace Präfix `Imports` ist in dem Sinn Global, dass es für den gesamten Code in der Datei verfügbar ist. Sie können Sie verwenden, wenn Sie XML-Element Literale erstellen und auf XML-Achsen Eigenschaften zugreifen. Weitere Informationen finden Sie unter [XML-Elementliterale](../xml-literals/xml-element-literal.md) und [XML-Achsen Eigenschaften](../xml-axis/index.md).

Wenn Sie einen globalen XML-Namespace ohne Namespace Präfix definieren (z. b `Imports <xmlns="http://SomeNameSpace>"` .), wird dieser Namespace als Standard-XML-Namespace betrachtet. Der Standard-XML-Namespace wird für alle XML-Element Literale oder XML-Attribut Achsen Eigenschaften verwendet, die nicht explizit einen Namespace angeben. Der Standard Namespace wird auch verwendet, wenn der angegebene Namespace der leere Namespace ist (d `xmlns=""` . h.). Der Standard-XML-Namespace gilt nicht für XML-Attribute in XML-Literalen oder XML-Attribut Achsen Eigenschaften, die keinen Namespace aufweisen.

XML-Namespaces, die in einem XML-Literaltyp definiert sind, die als *lokale XML-Namespaces*bezeichnet werden, haben Vorrang vor XML-Namespaces, die von der- `Imports` Anweisung als Global definiert werden. XML-Namespaces, die durch die-Anweisung definiert werden, haben `Imports` Vorrang vor XML-Namespaces, die für ein Visual Basic Projekt importiert werden. Wenn ein XML-Literale einen XML-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.

Globale XML-Namespaces befolgen dieselben Bereichs-und Definitions Regeln wie .NET Framework Namespaces. Daher können Sie eine- `Imports` Anweisung einschließen, um einen globalen XML-Namespace zu definieren, wo Sie einen .NET Framework-Namespace importieren können. Dies gilt sowohl für Code Dateien als auch für importierte Namespaces auf Projektebene. Weitere Informationen zu importierten Namespaces auf Projektebene finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).

Jede Quelldatei kann eine beliebige Anzahl von- `Imports` Anweisungen enthalten. Diese müssen auf Options Deklarationen folgen, wie z. b. die `Option Strict` -Anweisung, und Sie müssen vor Programmierungs Element Deklarationen wie- `Module` oder-Anweisungen stehen `Class` .

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden ein Standard-XML-Namespace und ein XML-Namespace importiert, die mit dem Präfix identifiziert werden `ns` . Anschließend werden XML-Literale erstellt, die beide Namespaces verwenden.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

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

Im folgenden Beispiel wird das XML-Namespace Präfix importiert `ns` . Anschließend wird ein XML-wahrsten erstellt, das das Namespace Präfix verwendet und die endgültige Form des Elements anzeigt.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Durch diesen Code wird folgender Text angezeigt:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Beachten Sie, dass der Compiler das XML-Namespace Präfix aus einem globalen Präfix in eine lokale Präfix Definition konvertiert hat.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird das XML-Namespace Präfix importiert `ns` . Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

Durch diesen Code wird folgender Text angezeigt:

`Patrick Hines`

## <a name="see-also"></a>Weitere Informationen

- [XML-Elementliteral](../xml-literals/xml-element-literal.md)
- [XML-Achseneigenschaften](../xml-axis/index.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [GetXmlNamespace-Operator](../operators/getxmlnamespace-operator.md)
