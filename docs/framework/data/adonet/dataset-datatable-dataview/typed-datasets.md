---
title: Typisierte "DataSets"
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 4648d49b1d7419d61a3a000404f42e0d02d25786
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198444"
---
# <a name="typed-datasets"></a><span data-ttu-id="fbc2e-102">Typisierte "DataSets"</span><span class="sxs-lookup"><span data-stu-id="fbc2e-102">Typed DataSets</span></span>

<span data-ttu-id="fbc2e-103">Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="fbc2e-104">Auf Tabellen und Spalten, die Teil des **DataSets** sind, kann mit benutzerfreundlichen Namen und stark typisierten Variablen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="fbc2e-105">Ein typisiertes **DataSet** ist eine Klasse, die von einem **DataSet**abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="fbc2e-106">Daher erbt Sie alle Methoden, Ereignisse und Eigenschaften eines **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="fbc2e-107">Darüber hinaus stellt ein typisiertes **DataSet** stark typisierte Methoden, Ereignisse und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="fbc2e-108">Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="fbc2e-109">Abgesehen von der verbesserten Lesbarkeit des Codes ermöglicht ein typisiertes **DataSet** auch dem Visual Studio .NET-Code-Editor das automatische Vervollständigen von Zeilen während der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="fbc2e-110">Außerdem ermöglicht das stark typisierte **DataSet** den Zugriff auf Werte als richtigen Typ zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="fbc2e-111">Bei einem **DataSet**mit starker Typisierung werden Typen Konflikt Fehler abgefangen, wenn der Code kompiliert wird, anstatt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbc2e-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fbc2e-112">In This Section</span></span>  

 [<span data-ttu-id="fbc2e-113">Generieren von stark typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="fbc2e-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="fbc2e-114">Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="fbc2e-115">Hinzufügen von Anmerkungen zu typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="fbc2e-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="fbc2e-116">Beschreibt, wie das XSD-Schema (XML Schema Definition Language) mit Anmerkungen versehen wird, das zum Generieren eines stark typisierten **DataSets**verwendet wird, um **DataSet** -Elementen anzeigen Amen zu übergeben, ohne das zugrunde liegende Schema zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc2e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbc2e-117">See also</span></span>

- [<span data-ttu-id="fbc2e-118">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="fbc2e-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="fbc2e-119">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fbc2e-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
