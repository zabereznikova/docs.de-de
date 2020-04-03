---
title: Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10
description: In diesem Artikel wird beschrieben, wie Sie Apps unterstützen, die das von vielen Windows-Betriebssystemversionen nicht mehr unterstützte NET Framework 1.1 benötigen.
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111789"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10

.NET Framework 1.1 wird von den Betriebssystemen Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 oder Windows 10 nicht unterstützt. In einigen Fällen wird .NET Framework 1.1 jedoch benötigt, um eine App auszuführen. Wenden Sie sich in solchen Fällen an Ihren unabhängigen Softwareanbieter (ISV), um die App so aktualisieren zu lassen, dass sie in .NET Framework 3.5 SP1 oder höher ausgeführt werden kann. Weitere Informationen finden Sie unter [Migrieren von .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a>Installieren von .NET Framework 1.1 von einer CD oder über das Download Center

NET Framework 1.1 kann unter Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 oder Windows 10 nicht manuell von einer CD oder über das Download Center installiert werden. Diese Frameworkversion wird nicht mehr unterstützt. Wenn Sie versuchen, das Paket zu installieren, wird die folgende Fehlermeldung angezeigt: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one." (Das Setup kann nicht fortgesetzt werden, da die Version des .NET Framework nicht mit einer bereits installierten Version kompatibel ist.) Installieren Sie [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22), um dieses Problem zu lösen. Diese Frameworkversion umfasst .NET Framework 2.0 (die Folgeversion von .NET Framework 1.1), die unter Windows 8, Windows 8.1 und Windows 10 unterstützt wird. Sie sollten zunächst immer versuchen, die App zu installieren, um herauszufinden, ob eine automatische Aktualisierung auf eine höhere Version von .NET Framework durchgeführt werden kann. Falls dies nicht möglich ist, wenden Sie sich an Ihren ISV, um ein Update für die App anzufordern.

## <a name="see-also"></a>Siehe auch

- [Migrieren von .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8](dotnet-35-windows-10.md)
