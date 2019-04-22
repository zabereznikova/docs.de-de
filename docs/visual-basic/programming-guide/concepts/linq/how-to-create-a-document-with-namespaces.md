---
title: 'Vorgehensweise: Erstellen eines Dokuments mit Namespaces (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: b65d22451d900f7b20226f25b61bb235241dd84f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816861"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a><span data-ttu-id="13322-102">Vorgehensweise: Erstellen eines Dokuments mit Namespaces (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13322-102">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="13322-103">In diesem Thema wird das Erstellen eines Dokuments mit Namespaces in Visual Basic beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13322-103">This topic shows how to create a document with namespaces in Visual Basic.</span></span>  
  
 <span data-ttu-id="13322-104">Bei Verwendung von XML-Literalen in Visual Basic können Benutzer einen globalen XML-Standardnamespace definieren.</span><span class="sxs-lookup"><span data-stu-id="13322-104">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="13322-105">Dieser Namespace ist der Standardnamespace für die XML-Literale und für die XML-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="13322-105">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="13322-106">Der XML-Standardnamespace kann auf Projekt- oder auf Dateiebene definiert werden.</span><span class="sxs-lookup"><span data-stu-id="13322-106">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="13322-107">Bei Definition auf Dateiebene wird der auf der Projektebene definierte Standardnamespace außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="13322-107">If it is defined at the file level, it overrides the default namespace at the project level.</span></span>  
  
 <span data-ttu-id="13322-108">Sie können auch andere Namespaces definieren und die Namespacepräfixe für diese Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="13322-108">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span>  
  
 <span data-ttu-id="13322-109">Standardnamespaces und Namespaces mit einem Präfix werden mit dem `Imports`-Schlüsselwort definiert.</span><span class="sxs-lookup"><span data-stu-id="13322-109">You define both default namespaces and namespaces with a prefix by using the `Imports` keyword.</span></span>  
  
 <span data-ttu-id="13322-110">Weitere Informationen finden Sie unter [Einführung in die XML-Literale in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span><span class="sxs-lookup"><span data-stu-id="13322-110">For more information, see [Introduction to XML Literals in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span></span>  
  
 <span data-ttu-id="13322-111">Beachten Sie, dass der XML-Standardnamespace nur für Elemente, nicht aber für Attribute gültig ist.</span><span class="sxs-lookup"><span data-stu-id="13322-111">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="13322-112">Attribute befinden sind standardmäßig nie in einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="13322-112">Attributes are by default always in no namespace.</span></span> <span data-ttu-id="13322-113">Sie können aber ein Namespacepräfix verwenden, um ein Attribut in einen Namespace zu setzen.</span><span class="sxs-lookup"><span data-stu-id="13322-113">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13322-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13322-114">Example</span></span>  
 <span data-ttu-id="13322-115">Dieses Beispiel erstellt ein Dokument, das einen Namespace enthält:</span><span class="sxs-lookup"><span data-stu-id="13322-115">This example creates a document that contains a namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="13322-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="13322-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="13322-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13322-117">Example</span></span>  
 <span data-ttu-id="13322-118">Dieses Beispiel erstellt ein Dokument, das zwei Namespaces enthält, wovon ein Namespace der Standardnamespace ist:</span><span class="sxs-lookup"><span data-stu-id="13322-118">This example creates a document that contains two namespaces, one of which is the default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="13322-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="13322-119">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="13322-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13322-120">Example</span></span>  
 <span data-ttu-id="13322-121">Das folgende Beispiel erstellt ein Dokument, das zwei Namespaces enthält, die beide ein Namespacepräfix besitzen.</span><span class="sxs-lookup"><span data-stu-id="13322-121">The following example creates a document that contains multiple namespaces, both with namespace prefixes.</span></span>  
  
 <span data-ttu-id="13322-122">Beim Serialisieren in eine XML-Struktur gibt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] je nach Bedarf Namespacedeklarationen aus, sodass sich jedes Element in dem für ihn vorgesehenen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="13322-122">When serializing an XML tree, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] emits namespace declarations as required so that each element is in its designated namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="13322-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="13322-123">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13322-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13322-124">See also</span></span>

- [<span data-ttu-id="13322-125">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13322-125">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
