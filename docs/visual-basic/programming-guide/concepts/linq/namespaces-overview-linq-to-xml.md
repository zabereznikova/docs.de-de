---
title: "Übersicht über Namespaces (LINQ to XML) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e9536615871b83099a11e46125ed85b44d9335d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-overview-linq-to-xml"></a><span data-ttu-id="05d69-102">Übersicht über Namespaces (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="05d69-102">Namespaces Overview (LINQ to XML)</span></span>
<span data-ttu-id="05d69-103">In diesem Thema werden die Namespaces, die <xref:System.Xml.Linq.XName>Klasse, und die <xref:System.Xml.Linq.XNamespace>Klasse.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="05d69-103">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>  
  
## <a name="xml-names"></a><span data-ttu-id="05d69-104">XML-Namen</span><span class="sxs-lookup"><span data-stu-id="05d69-104">XML Names</span></span>  
 <span data-ttu-id="05d69-105">XML-Namen sind häufig die Ursache für komplexe Konstruktionen bei der XML-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="05d69-105">XML names are often a source of complexity in XML programming.</span></span> <span data-ttu-id="05d69-106">Ein XML-Name besteht aus einem XML-Namespace (auch als XML-Namespace-URI bezeichnet) und einem lokalen Namen.</span><span class="sxs-lookup"><span data-stu-id="05d69-106">An XML name consists of an XML namespace (also called an XML namespace URI) and a local name.</span></span> <span data-ttu-id="05d69-107">Ein XML-Namespace ähnelt einem Namespace in einem auf [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] basierenden Programm.</span><span class="sxs-lookup"><span data-stu-id="05d69-107">An XML namespace is similar to a namespace in a [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-based program.</span></span> <span data-ttu-id="05d69-108">Er ermöglicht die eindeutige Qualifizierung von Element- und Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="05d69-108">It enables you to uniquely qualify the names of elements and attributes.</span></span> <span data-ttu-id="05d69-109">Auf diese Weise lassen sich Namenskonflikte zwischen verschiedenen Teilen eines XML-Dokuments besser vermeiden.</span><span class="sxs-lookup"><span data-stu-id="05d69-109">This helps avoid name conflicts between various parts of an XML document.</span></span> <span data-ttu-id="05d69-110">Wenn Sie einen XML-Namespace deklariert haben, können Sie einen lokalen Namen auswählen, der nur innerhalb dieses Namespaces eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="05d69-110">When you have declared an XML namespace, you can select a local name that only has to be unique within that namespace.</span></span>  
  
 <span data-ttu-id="05d69-111">Ein anderer Aspekt von XML-Namen sind XML *Namespacepräfixe*.</span><span class="sxs-lookup"><span data-stu-id="05d69-111">Another aspect of XML names is XML *namespace prefixes*.</span></span> <span data-ttu-id="05d69-112">XML-Präfixe sind die Hauptursache für die Komplexität von XML-Namen.</span><span class="sxs-lookup"><span data-stu-id="05d69-112">XML prefixes cause most of the complexity of XML names.</span></span> <span data-ttu-id="05d69-113">Diese Präfixe ermöglichen es Ihnen, eine Kurzform eines XML-Namespace zu erstellen, wodurch das XML-Dokument kompakter und verständlicher wird.</span><span class="sxs-lookup"><span data-stu-id="05d69-113">These prefixes enable you to create a shortcut for an XML namespace, which makes the XML document more concise and understandable.</span></span> <span data-ttu-id="05d69-114">Die Bedeutung der XML-Präfixe ist jedoch kontextabhängig, was zur erhöhten Komplexität beiträgt.</span><span class="sxs-lookup"><span data-stu-id="05d69-114">However, XML prefixes depend on their context to have meaning, which adds complexity.</span></span> <span data-ttu-id="05d69-115">Das XML-Präfix `aw` kann z. B. in unterschiedlichen Teilen einer XML-Struktur unterschiedlichen XML-Namespaces zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="05d69-115">For example, the XML prefix `aw` could be associated with one XML namespace in one part of an XML tree, and with a different XML namespace in a different part of the XML tree.</span></span>  
  
 <span data-ttu-id="05d69-116">Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mit Visual Basic und XML-Literalen müssen Sie Namespacepräfixe verwenden, wenn Sie mit Dokumenten in Namespaces arbeiten.</span><span class="sxs-lookup"><span data-stu-id="05d69-116">When using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with Visual Basic and XML literals, you must use namespace prefixes when working with documents in namespaces.</span></span>  
  
 <span data-ttu-id="05d69-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], die Klasse, die XML-Namen ist <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="05d69-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the class that represents XML names is <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="05d69-118">XML-Namen treten häufig in der gesamten der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -API, und wo ein XML-Name erforderlich ist, wird Ihnen ein <xref:System.Xml.Linq.XName>Parameter.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="05d69-118">XML names appear frequently throughout the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, and wherever an XML name is required, you will find an <xref:System.Xml.Linq.XName> parameter.</span></span> <span data-ttu-id="05d69-119">Arbeiten Sie jedoch nur selten direkt mit einer <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="05d69-119">However, you rarely work directly with an <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="05d69-120"><xref:System.Xml.Linq.XName>enthält eine implizite Konvertierung aus einer Zeichenfolge.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="05d69-120"><xref:System.Xml.Linq.XName> contains an implicit conversion from string.</span></span>  
  
 <span data-ttu-id="05d69-121">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNamespace>und <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="05d69-121">For more information, see <xref:System.Xml.Linq.XNamespace> and <xref:System.Xml.Linq.XName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d69-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05d69-122">See Also</span></span>  
 [<span data-ttu-id="05d69-123">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05d69-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
