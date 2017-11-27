---
title: Modellieren und Zuordnen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2004b950f1096f574734259ba02944577dd9adc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="89802-102">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="89802-102">Modeling and Mapping</span></span>
<span data-ttu-id="89802-103">In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Sie das konzeptionelle Modell, das Speichermodell und die Zuordnung zwischen beiden auf die Weise definieren, die der Anwendung am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="89802-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="89802-104">Das Entity Data Model-Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] ermöglichen Ihnen die Erstellung einer.[ EDMX-Datei](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) aus einer Datenbank oder einem grafischen Modell und aktualisieren Sie dann die Datei, wenn die Datenbank oder das Modell ändert.</span><span class="sxs-lookup"><span data-stu-id="89802-104">The Entity Data Model Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] allow you to create an .[edmx file](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="89802-105">Ab Entity Framework 4.1 können Sie ein Modell anhand der Code First-Entwicklung auch programmgesteuert erstellen.</span><span class="sxs-lookup"><span data-stu-id="89802-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="89802-106">Es gibt zwei verschiedene Szenarien für die Code First-Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="89802-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="89802-107">In beiden Fällen definiert der Entwickler ein Modell, indem er .NET Framework-Klassendefinitionen codiert und dann optional zusätzliche Zuordnungen oder Konfigurationen mithilfe von Datenanmerkungen oder der Fluent-API angibt.</span><span class="sxs-lookup"><span data-stu-id="89802-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="89802-108">Weitere Informationen finden Sie unter [erstellen und Zuordnen eines konzeptionellen Modells](http://go.microsoft.com/fwlink/?LinkId=235016).</span><span class="sxs-lookup"><span data-stu-id="89802-108">For more information, see [Creating and Mapping a Conceptual Model](http://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="89802-109">Sie können auch den EDM-Generator, der in der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89802-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="89802-110">EdmGen.exe generiert die CSDL-, SSDL- und MSL-Dateien aus einer vorhandenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="89802-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="89802-111">Sie können Modell- und Zuordnungsinhalte auch manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="89802-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="89802-112">Weitere Informationen finden Sie unter [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span><span class="sxs-lookup"><span data-stu-id="89802-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>
