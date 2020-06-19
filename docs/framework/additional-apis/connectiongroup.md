---
title: ConnectionGroup-Klasse
description: Erfahren Sie mehr über die connectiongroup-Klasse, die Verbindungen im Service Point-Kontext gruppiert und verwendet wird, um den Kontext für Netzwerkressourcen in .net zu verwalten.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
ms.openlocfilehash: 7121713b26880f2490b40d59d92d431a567519b3
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989810"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="235b9-103">ConnectionGroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="235b9-103">ConnectionGroup Class</span></span>

<span data-ttu-id="235b9-104">Die `ConnectionGroup` -Klasse gruppiert eine Liste von Verbindungen innerhalb des <xref:System.Net.ServicePoint> Kontexts und wird verwendet, um Kontext für Netzwerkressourcen (z. b. Proxys und separate Clients) zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="235b9-104">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="235b9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="235b9-105">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="235b9-106">Die `ConnectionGroup` -Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="235b9-106">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="235b9-107">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="235b9-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="235b9-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="235b9-108">Requirements</span></span>

<span data-ttu-id="235b9-109">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="235b9-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="235b9-110">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="235b9-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="235b9-111">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="235b9-111">**.NET Framework versions:** Available since 2.0.</span></span>
