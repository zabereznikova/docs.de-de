---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 7963db9e05eca7a7a148228c6d2fbca0221ca870
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155678"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="f4a67-102">SQL Server Compact und LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f4a67-102">SQL Server Compact and LINQ to SQL</span></span>

<span data-ttu-id="f4a67-103">SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert wird.</span><span class="sxs-lookup"><span data-stu-id="f4a67-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="f4a67-104">Weitere Informationen finden Sie unter [Verwenden von SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="f4a67-104">For more information, see [Using SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="f4a67-105">In diesem Thema werden die Hauptunterschiede in der Verwendung, Konfiguration, den Featuresätzen und dem Umfang der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Unterstützung erläutert.</span><span class="sxs-lookup"><span data-stu-id="f4a67-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="f4a67-106">Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f4a67-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  

 <span data-ttu-id="f4a67-107">Standardmäßig ist SQL Server Compact für alle Visual Studio-Editionen installiert und auf dem Entwicklungs Computer zur Verwendung mit verfügbar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4a67-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="f4a67-108">Die Bereitstellung einer Anwendung, die SQL Server Compact verwendet, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich jedoch von der Bereitstellung für eine SQL Server Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f4a67-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="f4a67-109">SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f4a67-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="f4a67-110">Beachten Sie die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f4a67-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="f4a67-111">SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4a67-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="f4a67-112">SQL Server Compact wird in demselben Prozess wie die Clientanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f4a67-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="f4a67-113">Die Effizienz der Kommunikation mit SQL Server Compact kann daher deutlich höher sein als die Kommunikation mit SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4a67-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="f4a67-114">Andererseits erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code (was mit den entsprechenden Kosten verbunden ist).</span><span class="sxs-lookup"><span data-stu-id="f4a67-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="f4a67-115">Die SQL Server Compact-DLL weist eine geringe Größe auf.</span><span class="sxs-lookup"><span data-stu-id="f4a67-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="f4a67-116">Diese Funktion verringert die Gesamtgröße der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f4a67-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="f4a67-117">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="f4a67-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="f4a67-118">Der objektrelationaler Designer unterstützt SQL Server Compact nicht.</span><span class="sxs-lookup"><span data-stu-id="f4a67-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="f4a67-119">Funktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="f4a67-119">Feature Set</span></span>  

 <span data-ttu-id="f4a67-120">Die SQL Server Compact Featuregruppe ist in den folgenden Punkten, die sich auf Anwendungen auswirken können, viel einfacher als die Funktionsgruppe von SQL Server [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f4a67-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="f4a67-121">SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.</span><span class="sxs-lookup"><span data-stu-id="f4a67-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="f4a67-122">SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f4a67-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="f4a67-123">SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.</span><span class="sxs-lookup"><span data-stu-id="f4a67-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="f4a67-124">SQL Server Compact bietet nur einen minimalen Optimierer.</span><span class="sxs-lookup"><span data-stu-id="f4a67-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="f4a67-125">Es ist möglich, dass es bei einigen Abfragen zu Zeitüberschreitungen kommt.</span><span class="sxs-lookup"><span data-stu-id="f4a67-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="f4a67-126">SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="f4a67-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a67-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4a67-127">See also</span></span>

- [<span data-ttu-id="f4a67-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="f4a67-128">Reference</span></span>](reference.md)
