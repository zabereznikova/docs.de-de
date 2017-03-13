---
title: "Imports Statement (XML Namespace) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ImportsXmlns"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML namespace [Visual Basic], importing"
  - "imports [Visual Basic]"
  - "Imports statement [Visual Basic]"
  - "namespaces [Visual Basic], importing"
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Imports Statement (XML Namespace)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Importiert XML\-Namespacepräfixe zur Verwendung in XML\-Literalen und XML\-Achseneigenschaften.  
  
## Syntax  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## Teile  
 `xmlNamespacePrefix`  
 Optional.  Die Zeichenfolge, durch die XML\-Elemente und Attribute auf `xmlNamespaceName` verweisen können.  Wenn Sie keinen `xmlNamespacePrefix` angeben, wird der XML\-Standardnamespace importiert.  Muss ein gültiger XML\-Bezeichner sein.  Weitere Informationen finden Sie unter [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Erforderlich.  Die Zeichenfolge, die den zu importierenden XML\-Namespace angibt.  
  
## Hinweise  
 Mit der `Imports`\-Anweisung können Sie globale XML\-Namespaces definieren, die Sie für XML\-Literale und XML\-Achseneigenschaften oder als Parameter für den Operator `GetXmlNamespace` verwenden können.  \(Informationen zur Verwendung der `Imports`\-Anweisung zum Importieren eines Alias, den Sie an den Stellen verwenden können, an denen im Code Typnamen verwendet werden, finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).\) Die Syntax zum Deklarieren eines XML\-Namespaces mit der `Imports`\-Anweisung ist identisch mit der in XML verwendeten Syntax.  Daher können Sie eine Namespacedeklaration aus einer XML\-Datei kopieren und in einer `Imports`\-Anweisung verwenden.  
  
 XML\-Namespacepräfixe sind hilfreich, wenn Sie wiederholt XML\-Elemente erstellen möchten, die aus demselben Namespace stammen.  Ein mit der `Imports`\-Anweisung deklarierter XML\-Namespace ist in dem Sinne global, dass er für den gesamten Code in der Datei zur Verfügung steht.  Sie können ihn beim Erstellen von XML\-Elementliteralen und beim Zugreifen auf XML\-Achseneigenschaften verwenden.  Weitere Informationen finden Sie unter [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Wenn Sie einen globalen XML\-Namespace ohne einen Namespacepräfix definieren \(z. B. `Imports <xmlns="http://SomeNameSpace>"`\), wird dieser Namespace als der XML\-Standardnamespace angesehen.  Der XML\-Standardnamespace wird für alle XML\-Elementliterale oder XML\-Attributachseneigenschaften verwendet, für die kein expliziter Namespace angegeben wird.  Außerdem wird der Standardnamespace verwendet, wenn ein leerer Namespace \(also `xmlns=""`\) angegeben wird.  Der XML\-Standardnamespace gilt nicht für XML\-Attribute in XML\-Literalen oder für XML\-Attributachseneigenschaften ohne Namespace.  
  
 In einem XML\-Literal definierte XML\-Namespaces, die als *lokale XML\-Namespaces* bezeichnet werden, haben Vorrang vor XML\-Namespaces, die mit der `Imports`\-Anweisung als global definiert werden.  Mit der `Imports`\-Anweisung definierte XML\-Namespaces haben Vorrang vor XML\-Namespaces, die für ein Visual Basic\-Projekt importiert werden.  Wenn ein XML\-Literal einen XML\-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.  
  
 Globale XML\-Namespaces folgen denselben Bereichs\- und Definitionsregeln wie .NET Framework\-Namespaces.  Aus diesem Grund können Sie eine `Imports`\-Anweisung zum Definieren eines globalen XML\-Namespaces auch an den Stellen angeben, an denen Sie einen .NET Framework\-Namespace importieren können.  Dies gilt sowohl für Codedateien als auch für auf Projektebene importierte Namespaces.  Informationen über auf Projektebene importierte Namespaces finden Sie unter [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Jede Quelldatei kann beliebig viele `Imports`\-Anweisungen enthalten.  Diese müssen nach Option\-Deklarationen, z. B. `Option Strict`, angegeben werden und Deklarationen von Programmierelementen, z. B. `Module`\-Anweisungen oder `Class`\-Anweisungen, vorangestellt werden.  
  
## Beispiel  
 Im folgenden Beispiel werden ein XML\-Standardnamespace und ein mit dem Präfix `ns` gekennzeichneter XML\-Namespace importiert.  Anschließend werden XML\-Literale erstellt, die beide Namespaces verwenden.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## Beispiel  
 Im folgenden Beispiel wird der XML\-Namespacepräfix `ns` importiert.  Anschließend wird ein XML\-Literal erstellt, das das Namespacepräfix verwendet und die abschließende Form des Elements anzeigt.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Beachten Sie, dass das XML\-Namespacepräfix vom Compiler von einer globalen Präfixdefinition in eine lokale Präfixdefinition umgewandelt wurde.  
  
## Beispiel  
 Im folgenden Beispiel wird der XML\-Namespacepräfix `ns` importiert.  Anschließend wird mit dem Namespacepräfix ein XML\-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## Siehe auch  
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [GetXmlNamespace Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)