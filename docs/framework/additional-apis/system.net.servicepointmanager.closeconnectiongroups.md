---
title: ServicePointManager. closeconnectiongroups-Methode (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990449"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="14981-102">ServicePointManager. closeconnectiongroups-Methode</span><span class="sxs-lookup"><span data-stu-id="14981-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="14981-103">Durchläuft alle Dienst Punkte und schließt Verbindungs Gruppen mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="14981-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="14981-104">Diese Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14981-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="14981-105">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="14981-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="14981-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="14981-106">Parameters</span></span>

<span data-ttu-id="14981-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="14981-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="14981-108">Der Name der Verbindungsgruppe, die geschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="14981-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="14981-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14981-109">Requirements</span></span>

<span data-ttu-id="14981-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="14981-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="14981-111">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="14981-111">**Assembly:** System (in System.dll)</span></span>
