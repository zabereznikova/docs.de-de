---
title: Teilweise Vertrauenswürdigkeit
ms.date: 03/30/2017
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
ms.openlocfilehash: f4eace87593f2b4c45101bafa0843998a093cbd5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579149"
---
# <a name="partial-trust"></a><span data-ttu-id="f8b7d-102">Teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="f8b7d-102">Partial Trust</span></span>

<span data-ttu-id="f8b7d-103">Beginnend mit dem .NET Framework 3,5 können teilweise vertrauenswürdige Aufrufer auf öffentliche Typen und Methoden zugreifen, die in <xref:System.ServiceModel> , und implementiert sind <xref:System.Runtime.Serialization> <xref:System.ServiceModel.Web> .</span><span class="sxs-lookup"><span data-stu-id="f8b7d-103">Starting with the .NET Framework 3.5, partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="f8b7d-104">In diesem Abschnitt werden die unterstützten Szenarien für die Verwendung von Windows Communication Foundation (WCF) in einer teilweise vertrauenswürdigen Anwendung sowie die begrenzte Teilmenge der WCF-Funktionalität beschrieben, die für Anwendungen mit reduzierten Berechtigungen für die Code Zugriffssicherheit (CAS) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f8b7d-104">This section describes supported scenarios for using Windows Communication Foundation (WCF) within a partially trusted application as well as the limited subset of WCF functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8b7d-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f8b7d-105">In This Section</span></span>  
 [<span data-ttu-id="f8b7d-106">Unterstützte Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="f8b7d-106">Supported Deployment Scenarios</span></span>](supported-deployment-scenarios.md)  
 <span data-ttu-id="f8b7d-107">Beschreibt die wichtigsten Szenarien mit teilweiser Vertrauenswürdigkeit für die Ausführung von WCF.</span><span class="sxs-lookup"><span data-stu-id="f8b7d-107">Describes the main partial trust scenarios for running WCF.</span></span>  
  
 [<span data-ttu-id="f8b7d-108">Funktionskompatibilität für teilweise Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="f8b7d-108">Partial Trust Feature Compatibility</span></span>](partial-trust-feature-compatibility.md)  
 <span data-ttu-id="f8b7d-109">Beschreibt die WCF-Funktionen, die mit teilweiser Vertrauenswürdigkeit nicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f8b7d-109">Describes the WCF features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="f8b7d-110">Empfehlungen für eine teilweise vertrauenswürdige Umgebung</span><span class="sxs-lookup"><span data-stu-id="f8b7d-110">Partial Trust Best Practices</span></span>](partial-trust-best-practices.md)  
 <span data-ttu-id="f8b7d-111">Enthält bewährte Methoden für die Verwendung von WCF in teilweise vertrauenswürdigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f8b7d-111">Contains best practices for using WCF in partially trusted applications.</span></span>
