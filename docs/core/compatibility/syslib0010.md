---
title: Warnung SYSLIB0010
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0010 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dcd331aa5c68381ea29848bc54ee4b1a5e75330d
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333059"
---
# <a name="syslib0010-unsupported-remoting-apis"></a><span data-ttu-id="979fe-103">SYSLIB0010: Nicht unterstützte Remoting-APIs</span><span class="sxs-lookup"><span data-stu-id="979fe-103">SYSLIB0010: Unsupported remoting APIs</span></span>

<span data-ttu-id="979fe-104">[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie, und die Infrastruktur dafür ist nur im .NET Framework vorhanden.</span><span class="sxs-lookup"><span data-stu-id="979fe-104">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology, and the infrastructure exists only in .NET Framework.</span></span> <span data-ttu-id="979fe-105">Die folgenden Remoting-APIs sind ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="979fe-105">The following remoting-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="979fe-106">Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0010` hervor.</span><span class="sxs-lookup"><span data-stu-id="979fe-106">Using them in code generates warning `SYSLIB0010` at compile time.</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a><span data-ttu-id="979fe-107">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="979fe-107">Workaround</span></span>

<span data-ttu-id="979fe-108">Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="979fe-108">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="979fe-109">Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="979fe-109">For more information, see [.NET Framework technologies unavailable on .NET Core](../porting/net-framework-tech-unavailable.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="979fe-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="979fe-110">See also</span></span>

- <span data-ttu-id="979fe-111">[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span><span class="sxs-lookup"><span data-stu-id="979fe-111">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span></span>
