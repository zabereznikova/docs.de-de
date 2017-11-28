---
title: Parsen von XML (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d262fd2177ac77ab5109362f94cc51d03c9563c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-xml-c"></a><span data-ttu-id="eacbc-102">Parsen von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-102">Parsing XML (C#)</span></span>
<span data-ttu-id="eacbc-103">In den Themen in diesem Abschnitt wird das Analysieren von XML-Dokumenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eacbc-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eacbc-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eacbc-104">In This Section</span></span>  
  
|<span data-ttu-id="eacbc-105">Thema</span><span class="sxs-lookup"><span data-stu-id="eacbc-105">Topic</span></span>|<span data-ttu-id="eacbc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eacbc-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="eacbc-107">Vorgehensweise: Parsen einer Zeichenfolge (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="eacbc-108">Zeigt, wie eine Zeichenfolge zum Erstellen einer XML-Struktur analysiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eacbc-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="eacbc-109">Vorgehensweise: Laden von XML aus einer Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="eacbc-110">Zeigt, wie mit der <xref:System.Xml.Linq.XElement.Load%2A>-Methode XML-Code aus einem URI geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eacbc-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="eacbc-111">Beibehalten von Leerzeichen beim Laden oder Parsen von XML</span><span class="sxs-lookup"><span data-stu-id="eacbc-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="eacbc-112">Beschreibt, wie das Leerraumverhalten von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] beim Laden von XML-Strukturen gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eacbc-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="eacbc-113">Vorgehensweise: Auffangen von Parsingfehlern (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="eacbc-114">Zeigt, wie nicht wohlgeformtes oder ungültiges XML erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eacbc-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="eacbc-115">Vorgehensweise: Erstellen einer Struktur aus XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="eacbc-116">Zeigt, wie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eacbc-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="eacbc-117">Vorgehensweise: Streamen von XML-Fragmenten aus einem XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="eacbc-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="eacbc-118">Zeigt, wie XML-Fragmente mit einem <xref:System.Xml.XmlReader> gestreamt werden können.</span><span class="sxs-lookup"><span data-stu-id="eacbc-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="eacbc-119">Wenn Sie willkürlich große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="eacbc-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="eacbc-120">Stattdessen können Sie XML-Fragmente streamen.</span><span class="sxs-lookup"><span data-stu-id="eacbc-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eacbc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eacbc-121">See Also</span></span>  
 [<span data-ttu-id="eacbc-122">Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="eacbc-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
