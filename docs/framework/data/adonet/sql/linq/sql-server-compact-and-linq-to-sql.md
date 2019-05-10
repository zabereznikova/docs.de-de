---
title: SQL Server Compact und LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: a0cb45b31f7134264068297f54013f49b35f669d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651202"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="4bb77-102">SQL Server Compact und LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bb77-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="4bb77-103">SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="4bb77-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="4bb77-104">Weitere Informationen finden Sie unter [mithilfe von SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="4bb77-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="4bb77-105">In diesem Thema wird beschrieben, die wichtigsten Unterschiede in Verwendung, Konfiguration, Funktionsgruppen und Rahmen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4bb77-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="4bb77-106">Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bb77-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="4bb77-107">Standardmäßig SQL Server Compact wird für alle Editionen von Visual Studio installiert und steht daher auf dem Entwicklungscomputer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bb77-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4bb77-108">Aber die Bereitstellung einer Anwendung, die SQL Server Compact verwendet und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich von dem für eine SQL Server-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4bb77-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="4bb77-109">SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="4bb77-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="4bb77-110">Beachten Sie die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4bb77-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="4bb77-111">SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bb77-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="4bb77-112">SQL Server Compact im selben Prozess wie die Clientanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4bb77-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="4bb77-113">Die Effizienz der Kommunikation mit SQL Server Compact kann deshalb bedeutend höher als die Kommunikation mit SQL Server sein.</span><span class="sxs-lookup"><span data-stu-id="4bb77-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="4bb77-114">Andererseits, erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code mit den entsprechenden Kosten verbunden.</span><span class="sxs-lookup"><span data-stu-id="4bb77-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="4bb77-115">Die Größe der SQL Server Compact-DLL ist klein.</span><span class="sxs-lookup"><span data-stu-id="4bb77-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="4bb77-116">Diese Funktion verringert die Gesamtgröße der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4bb77-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="4bb77-117">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4bb77-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="4bb77-118">Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bietet keine Unterstützung für SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4bb77-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="4bb77-119">Funktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="4bb77-119">Feature Set</span></span>  
 <span data-ttu-id="4bb77-120">Der SQL Server Compact-Funktionsgruppe ist viel einfacher als die Funktionsgruppe von SQL Server auf folgende Weise, die beeinflussen können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="4bb77-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="4bb77-121">SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.</span><span class="sxs-lookup"><span data-stu-id="4bb77-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="4bb77-122">SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4bb77-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="4bb77-123">SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.</span><span class="sxs-lookup"><span data-stu-id="4bb77-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="4bb77-124">SQL Server Compact bietet nur einen minimalen Optimierer.</span><span class="sxs-lookup"><span data-stu-id="4bb77-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="4bb77-125">Es ist möglich, dass einige Abfragen zu zeitüberschreitungen kommt.</span><span class="sxs-lookup"><span data-stu-id="4bb77-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="4bb77-126">SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="4bb77-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb77-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bb77-127">See also</span></span>

- [<span data-ttu-id="4bb77-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="4bb77-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
