---
title: Zuverlässigkeit
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acb84c6617cdffabfe276895f81e7df2b04bb8bb
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046237"
---
# <a name="reliability"></a><span data-ttu-id="c0194-102">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="c0194-102">Reliability</span></span>
<span data-ttu-id="c0194-103">Code, der in Serverumgebungen wie SQL Server ausgeführt wird, muss unbedingt vor asynchronen Ausnahmen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="c0194-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="c0194-104">Die in diesem Thema dargestellte Zuverlässigkeit ist nicht nur für SQL Server relevant, sondern für jeden Host, der in einer .NET Framework-Umgebung Version 2.0 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c0194-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="c0194-105">Da jedoch SQL Server der erste Dienst ist, der die neuen Zuverlässigkeitsfunktionen von Version 2.0 umfassend verwendet, dient es hier als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c0194-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="c0194-106">In SQL Server ausgeführter Code unterliegt strengeren Richtlinien zur Zuverlässigkeit als andere Serverumgebungen.</span><span class="sxs-lookup"><span data-stu-id="c0194-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="c0194-107">Dies liegt daran, dass SQL Server ständig am Rand des Ressourcenverbrauchs betrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c0194-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="c0194-108">Die Ausnahmen <xref:System.OutOfMemoryException> und <xref:System.Threading.ThreadAbortException> sind für die SQL Server-Umgebung nicht ungewöhnlich.</span><span class="sxs-lookup"><span data-stu-id="c0194-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="c0194-109">Diese Richtlinien betreffen im Allgemeinen weniger die Zuverlässigkeit, sondern sind vielmehr darauf ausgerichtet, voll vertrauenswürdigen verwalteten Code bei Wiederverwendung auf <xref:System.AppDomain>-Ebene ordnungsgemäß abzubrechen. So hält der Server auf einfache Weise die Konsistenz und Verfügbarkeit aufrecht.</span><span class="sxs-lookup"><span data-stu-id="c0194-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0194-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c0194-110">In This Section</span></span>  
 [<span data-ttu-id="c0194-111">SQL Server Programming and Host Protection Attributes (SQL Server-Programmierung und Hostschutzattribute)</span><span class="sxs-lookup"><span data-stu-id="c0194-111">SQL Server Programming and Host Protection Attributes</span></span>](sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="c0194-112">Beschreibt, wie SQL Server das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut verwendet, um die Ausführung von verwaltetem Code einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="c0194-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="c0194-113">Empfohlene Vorgehensweisen für die Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="c0194-113">Reliability Best Practices</span></span>](reliability-best-practices.md)  
 <span data-ttu-id="c0194-114">Enthält Richtlinien zum Schreiben von Code, der die Zuverlässigkeitsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c0194-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="c0194-115">Eingeschränkte Ausführungsbereiche</span><span class="sxs-lookup"><span data-stu-id="c0194-115">Constrained Execution Regions</span></span>](constrained-execution-regions.md)  
 <span data-ttu-id="c0194-116">Beschreibt die Funktion und das Verhalten von eingeschränkten Ausführungsbereichen (Constrained Execution Regions, CERs).</span><span class="sxs-lookup"><span data-stu-id="c0194-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0194-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="c0194-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
