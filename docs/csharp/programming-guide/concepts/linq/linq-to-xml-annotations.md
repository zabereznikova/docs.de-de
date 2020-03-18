---
title: LINQ to XML-Anmerkungen 3
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 5f1940be2fc126ff9e9c7a4cb37e5cc7fc95d3c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "66689942"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="85c4e-102">LINQ to XML-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="85c4e-102">LINQ to XML Annotations</span></span>

<span data-ttu-id="85c4e-103">Mit Anmerkungen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Objekte eines beliebigen Typs mit jeder beliebigen XML-Komponente in einer XML-Struktur verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="85c4e-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="85c4e-104">Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, wie einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XAttribute>, rufen Sie die <xref:System.Xml.Linq.XObject.AddAnnotation%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="85c4e-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="85c4e-105">Anmerkungen werden nach Typ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="85c4e-105">You retrieve annotations by type.</span></span>

<span data-ttu-id="85c4e-106">Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="85c4e-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="85c4e-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="85c4e-107">Methods</span></span>

<span data-ttu-id="85c4e-108">Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="85c4e-108">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="85c4e-109">Methode</span><span class="sxs-lookup"><span data-stu-id="85c4e-109">Method</span></span>|<span data-ttu-id="85c4e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85c4e-110">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="85c4e-111">Fügt der Anmerkungsliste eines <xref:System.Xml.Linq.XObject> ein Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="85c4e-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="85c4e-112">Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="85c4e-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="85c4e-113">Ruft eine Auflistung von Anmerkungen des angegebenen Typs für ein <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="85c4e-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="85c4e-114">Entfernt die Anmerkungen des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="85c4e-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
