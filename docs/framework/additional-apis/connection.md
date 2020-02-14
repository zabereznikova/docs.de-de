---
title: Verbindungs Klasse (System.net)
ms.date: 05/01/2017
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
ms.openlocfilehash: e9e0f4eed5eb4a7efd27177ab65551afa87fb7f6
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215090"
---
# <a name="connection-class"></a><span data-ttu-id="3ad1d-102">Verbindungsklasse</span><span class="sxs-lookup"><span data-stu-id="3ad1d-102">Connection Class</span></span>

<span data-ttu-id="3ad1d-103">Die `Connection`-Klasse analysiert Server Antworten, Warteschlangen Anforderungen und Pipeline Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ad1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ad1d-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="3ad1d-105">Die `Connection`-Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="3ad1d-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ad1d-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ad1d-107">Requirements</span></span>

<span data-ttu-id="3ad1d-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3ad1d-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3ad1d-109">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="3ad1d-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="3ad1d-110">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-110">**.NET Framework versions:** Available since 2.0.</span></span>
