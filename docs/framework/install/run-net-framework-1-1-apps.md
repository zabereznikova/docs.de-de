---
title: Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ceaa3ea9d9140c6b5df45f067558da2de80b8dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535410"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Ausführen von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10

.NET Framework 1.1 wird von den Betriebssystemen [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht unterstützt. In manchen Fällen wird ausdrücklich angegeben, dass .NET Framework 1.1 zum Ausführen einer App notwendig ist. In solchen Fällen sollten Sie sich an den unabhängigen Softwareanbieter wenden und die App so aktualisieren lassen, dass sie unter [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] oder einer höheren Version ausgeführt werden kann. Weitere Informationen finden Sie unter [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Installieren von .NET Framework 1.1 von einem Datenträger CD oder über das Download Center

NET Framework 1.1 kann unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht manuell installiert werden. Er wird nicht mehr unterstützt. Wenn Sie versuchen, das Paket zu installieren, wird die folgende Fehlermeldung angezeigt: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one." (Das Setup kann nicht fortgesetzt werden, da die Version des .NET Framework nicht mit einer bereits installierten Version kompatibel ist.) Installieren Sie [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22), um dieses Problem zu beheben. Diese Version enthält .NET Framework 2.0 (die Folgeversion von .NET Framework 1.1), die unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] und Windows 10 unterstützt wird. Sie sollten immer versuchen, zunächst die App zu installieren, um herauszufinden, ob automatisch eine Aktualisierung auf eine höhere Version von .NET Framework durchgeführt wird. Wenn dies nicht der Fall ist, wenden Sie sich an den unabhängigen Softwareanbieter um ein Update für die App zu erhalten.

## <a name="see-also"></a>Siehe auch

- [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
- [Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)
