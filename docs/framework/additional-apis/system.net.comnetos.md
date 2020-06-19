---
title: Comnettos-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990483"
---
# <a name="comnetos-class"></a><span data-ttu-id="55878-102">Comnettos-Klasse</span><span class="sxs-lookup"><span data-stu-id="55878-102">ComNetOS class</span></span>

<span data-ttu-id="55878-103">Bietet Informationen zum aktuellen Betriebssystem, z. b. Version und Installationstyp (Client oder Server).</span><span class="sxs-lookup"><span data-stu-id="55878-103">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="55878-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="55878-104">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="55878-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55878-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="55878-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="55878-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="55878-107">IsWin7orLater-Feld</span><span class="sxs-lookup"><span data-stu-id="55878-107">IsWin7orLater field</span></span>

<span data-ttu-id="55878-108">Gibt an, ob die Betriebssystemversion Windows 7 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="55878-108">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="55878-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="55878-109">Requirements</span></span>

<span data-ttu-id="55878-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="55878-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="55878-111">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="55878-111">**Assembly:** System (in System.dll)</span></span>
