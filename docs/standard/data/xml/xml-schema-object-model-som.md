---
title: XML-Schemaobjektmodell (SOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a897a599-ffd1-43f9-8807-e58c8a7194cd
ms.openlocfilehash: 1de9fdf9950ba3ae356779ca802afb71f24a345e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290317"
---
# <a name="xml-schema-object-model-som"></a><span data-ttu-id="9a3ce-102">XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="9a3ce-102">XML Schema Object Model (SOM)</span></span>
<span data-ttu-id="9a3ce-103">Ein XML-Schema ist ein leistungsstarkes und komplexes Tool zum Erstellen und Validieren von Strukturen in XML-kompatiblen Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-103">An XML schema is a powerful and complex tool for creating and validating structure in compliant XML documents.</span></span> <span data-ttu-id="9a3ce-104">Wie bei der Datenmodellierung in einer relationalen Datenbank kann mithilfe eines Schemas die Struktur von XML-Dokumenten definiert werden. Dies erfolgt durch Festlegen der Elemente, die in Dokumenten verwendet werden dürfen, einschließlich der Struktur und der Typen, denen diese Elemente entsprechen müssen, um für dieses spezielle Schema gültig zu sein.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-104">Similar to data modeling in a relational database, a schema provides a way to define the structure of XML documents, by specifying the elements that can be used in the documents, as well as the structure and types that these elements must follow in order to be valid for that specific schema.</span></span>  
  
 <span data-ttu-id="9a3ce-105">Das SOM (Schema Object Model) stellt im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace eine Reihe von Klassen zur Verfügung, mit denen Sie ein Schema aus einer Datei auslesen oder programmgesteuert und speicherintern ein Schema erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-105">The Schema Object Model (SOM) provides a set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that allow you to read a schema from a file or to programmatically create a schema in-memory.</span></span> <span data-ttu-id="9a3ce-106">Das Schema kann durchlaufen, bearbeitet, kompiliert, validiert oder in eine Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-106">The schema can then be traversed, editing, compiled, validated, or written to a file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a3ce-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9a3ce-107">In This Section</span></span>  
 [<span data-ttu-id="9a3ce-108">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="9a3ce-108">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)  
 <span data-ttu-id="9a3ce-109">In diesem Abschnitt werden das SOM (Schema Object Model) und die von diesem bereitgestellten Funktionen und Klassen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-109">Describes the Schema Object Model (SOM) and the features and classes it provides.</span></span>  
  
 [<span data-ttu-id="9a3ce-110">Lesen und Schreiben von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="9a3ce-110">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)  
 <span data-ttu-id="9a3ce-111">In diesem Abschnitt wird erläutert, wie Sie XML-Schemata aus Dateien oder anderen Quellen lesen und schreiben.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-111">Describes how to read and write XML schemas from files or other sources.</span></span>  
  
 [<span data-ttu-id="9a3ce-112">Erstellen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="9a3ce-112">Building XML Schemas</span></span>](building-xml-schemas.md)  
 <span data-ttu-id="9a3ce-113">In diesem Abschnitt wird beschrieben, wie mithilfe von Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace XML-Schemata im Speicher erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-113">Describes how to use the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace to build XML schemas in-memory.</span></span>  
  
 [<span data-ttu-id="9a3ce-114">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="9a3ce-114">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)  
 <span data-ttu-id="9a3ce-115">In diesem Abschnitt wird beschrieben, wie ein XML-Schema durchlaufen wird, um auf die im SOM gespeicherten Elemente, Attribute und Typen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-115">Describes how to traverse an XML schema to access the elements, attributes, and types stored in the SOM.</span></span>  
  
 [<span data-ttu-id="9a3ce-116">Bearbeiten von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="9a3ce-116">Editing XML Schemas</span></span>](editing-xml-schemas.md)  
 <span data-ttu-id="9a3ce-117">In diesem Abschnitt wird das Bearbeiten eines XML-Schema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-117">Describes how to edit an XML schema.</span></span>  
  
 [<span data-ttu-id="9a3ce-118">Einfügen oder Importieren von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="9a3ce-118">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)  
 <span data-ttu-id="9a3ce-119">In diesem Abschnitt wird erläutert, wie andere XML-Schemata eingefügt oder importiert werden, die die Struktur des Schemas zu ergänzen, in das Sie eingefügt bzw. importiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a3ce-119">Describes how to include or import other XML schemas to supplement the structure of the schema that includes or imports them.</span></span>
