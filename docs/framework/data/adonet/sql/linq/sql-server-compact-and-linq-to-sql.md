---
title: SQL Server Compact und LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9409c17065b0421ec32a61352f9c0b975095ab44
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="1f5a7-102">SQL Server Compact und LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1f5a7-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="1f5a7-103">SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="1f5a7-104">Weitere Informationen finden Sie unter [PAVE über mithilfe von SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span><span class="sxs-lookup"><span data-stu-id="1f5a7-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="1f5a7-105">In diesem Thema werden die Hauptunterschiede hinsichtlich der Verwendung, Konfiguration, Funktionsgruppen und Umfang der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="1f5a7-106">Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1f5a7-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="1f5a7-107">Standardmäßig SQL Server Compact ist installiert für alle [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] Editionen und steht daher auf dem Entwicklungscomputer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f5a7-107">By default, SQL Server Compact is installed for all [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="1f5a7-108">Aber die Bereitstellung einer Anwendung, die SQL Server Compact verwendet und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterscheidet sich von dem für eine [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] application.</span></span> <span data-ttu-id="1f5a7-109">SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft-Website heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="1f5a7-110">Beachten Sie die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1f5a7-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="1f5a7-111">SQL Server Compact wird als DLL verpackt, die für Datenbankdateien (Erweiterung .sdf) direkt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="1f5a7-112">SQL Server Compact in demselben Prozess wie die Clientanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="1f5a7-113">Die Effizienz der Kommunikation mit SQL Server Compact kann deshalb bedeutend höher als bei der Kommunikation mit [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f5a7-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1f5a7-114">Andererseits, erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code mit den entsprechenden Kosten verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="1f5a7-115">Die SQL Server Compact-DLL ist klein.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="1f5a7-116">Diese Funktion verringert die Gesamtgröße der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="1f5a7-117">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit und das SQLMetal-Befehlszeilentool unterstützen SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="1f5a7-118">Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bietet keine Unterstützung für SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="1f5a7-119">Funktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1f5a7-119">Feature Set</span></span>  
 <span data-ttu-id="1f5a7-120">Die SQL Server Compact-Funktionsgruppe ist erheblich einfacher als die Funktionsgruppe von [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] auf folgende Weise, die beeinflussen können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="1f5a7-120">The SQL Server Compact feature set is much simpler than the feature set of [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="1f5a7-121">SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="1f5a7-122">SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="1f5a7-123">SQL Server Compact unterstützt nur eine Teilmenge von SQL-Konstrukten.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="1f5a7-124">SQL Server Compact bietet nur einen minimalen Optimierer.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="1f5a7-125">Es ist möglich, dass einige Abfragen zu zeitüberschreitungen.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="1f5a7-126">SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="1f5a7-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5a7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f5a7-127">See Also</span></span>  
 [<span data-ttu-id="1f5a7-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="1f5a7-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
