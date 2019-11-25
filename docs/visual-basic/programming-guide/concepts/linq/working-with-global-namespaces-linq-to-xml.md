---
title: Arbeiten mit globalen Namespaces (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: 80510e370e0a9c7ab27cb5177d9b547ead82715c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350993"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a>Arbeiten mit globalen Namespaces (Visual Basic) (LINQ to XML)
One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement. Mithilfe dieser Funktionen können Sie einen XML-Namespace, der einen Präfix verwendet, oder einen XML-Standardnamespace deklarieren.  
  
 Diese Möglichkeit erweist sich in zwei Situationen als hilfreich: Zum einen werden in XML-Literalen deklarierte Namespaces nicht in eingebettete Ausdrücke übertragen. Durch das Deklarieren globaler Namespaces verringert sich der Arbeitsaufwand, der erforderlich ist, wenn Sie eingebettete Ausdrücke mit Namespaces verwenden. Zum anderen müssen Sie globale Namespaces deklarieren, um Namespaces mit XML-Eigenschaften zu verwenden.  
  
 Sie können globale Namespaces auf Projektebene deklarieren. Globale Namespaces können auch auf der Modulebene deklariert werden, wobei die globalen Namespaces auf Projektebene außer Kraft gesetzt werden. Schließlich ist es auch möglich, globale Namespaces in einem XML-Literal außer Kraft zu setzen.  
  
 Bei Verwendung von XML-Literalen oder XML-Eigenschaften, die sich in global deklarierten Namespaces befinden, können Sie sich den erweiterten Namen der XML-Literale oder -Eigenschaften anzeigen lassen, indem Sie in Visual Studio mit der Maus darauf zeigen. Der erweiterte Name wird dann in einer QuickInfo angezeigt.  
  
 Mit der <xref:System.Xml.Linq.XNamespace>-Methode können Sie ein `GetXmlNamespace`-Objekt abrufen, das einem globalen Namespace entspricht.  
  
## <a name="examples-of-global-namespaces"></a>Beispiele für globale Namespaces  
 Das folgende Beispiel deklariert einen globalen Standardnamespace unter Verwendung der `Imports`-Anweisung und verwendet dann ein XML-Literal, um ein <xref:System.Xml.Linq.XElement>-Objekt in diesem Namespace zu deklarieren:  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 Das folgende Beispiel deklariert einen globalen Namespace mit einem Präfix und verwendet dann ein XML-Literal, um ein Element zu initialisieren:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a>Globale Namespaces und eingebettete Ausdrücke  
 Namespaces, die in XML-Literalen deklariert werden, werden nicht in eingebettete Ausdrücke übertragen. Das folgende Beispiel deklariert einen Standardnamespace. Anschließend verwendet das Beispiel einen eingebetteten Ausdruck für das `Child`-Element.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 Wie Sie sehen, enthalten die sich ergebenden XML-Daten eine Deklaration eines Standardnamespace, sodass sich das `Child`-Element nicht in einem Namespace befindet.  
  
 Sie können den Namespace im eingebetteten Ausdruck wie folgt neu deklarieren:  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 Dies ist jedoch umständlicher als die Verwendung des globalen Standardnamespace, der einen besseren Ansatz darstellt. Beim globalen Standardnamespace können Sie XML-Literale verwenden, ohne Namespaces zu deklarieren. Die sich ergebenden XML-Daten befinden sich im global deklarierten Standardnamespace.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a>Verwenden von Namespaces mit XML-Eigenschaften  
 Wenn Sie mit einer XML-Struktur arbeiten, die sich in einem Namespace befindet, und wenn Sie XML-Eigenschaften verwenden, müssen Sie einen globalen Namespace verwenden, damit sich die XML-Eigenschaften ebenfalls im korrekten Namespace befinden. Das folgende Beispiel deklariert eine XML-Struktur in einem Namespace. Anschließend gibt das Beispiel die Anzahl von `Child`-Elementen aus.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 Diesem Beispiel zufolge gibt es keine `Child`-Elemente. Es erzeugt die folgende Ausgabe:  
  
```console  
0  
```  
  
 Wenn Sie aber einen globalen Standardnamespace deklarieren, befinden sich sowohl das XML-Literal als auch die XML-Eigenschaft im globalen Standardnamespace:  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 Diesem Beispiel zufolge gibt es genau ein `Child`-Element. Es erzeugt die folgende Ausgabe:  
  
```console  
1  
```  
  
 Wenn Sie einen globalen Namespace deklarieren, der ein Präfix besitzt, können Sie das Präfix sowohl für die XML-Literale als auch für die XML-Eigenschaften verwenden:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a>XNamespace und globale Namespaces  
 Mit der <xref:System.Xml.Linq.XNamespace>-Methode können Sie ein `GetXmlNamespace`-Objekt abrufen:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```console  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a>Siehe auch

- [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
