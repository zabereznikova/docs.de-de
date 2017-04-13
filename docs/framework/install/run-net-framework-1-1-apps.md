---
title: "Ausf&#252;hren von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework 1.1, Ausführung unter Windows 8"
  - "Windows 8, Ausführen von .NET Framework 1.1-Apps"
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Ausf&#252;hren von auf .NET Framework 1.1 basierenden Apps auf Windows 8, Windows 8.1 oder Windows 10
.NET Framework 1.1 wird von den Betriebssystemen [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht unterstützt.  In manchen Fällen wird ausdrücklich angegeben, dass .NET Framework 1.1 zum Ausführen einer Anwendung notwendig ist.  In solchen Fällen sollten Sie sich an den unabhängigen Softwareanbieter wenden und die Anwendung so aktualisieren lassen, dass sie unter [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] oder einer höheren Version ausgeführt werden kann.  Weitere Informationen finden Sie unter [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).  
  
## Installieren von .NET Framework 1.1 von einem Datenträger CD oder über das Download Center  
 NET Framework 1.1 kann unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] oder Windows 10 nicht manuell installiert werden.  Er wird nicht mehr unterstützt.  Wenn Sie versuchen, das Paket zu installieren, wird die folgende Fehlermeldung angezeigt: "Setup kann nicht fortgesetzt werden, da diese Version von .NET Framework mit einer zuvor installierten Version inkompatibel ist". Installieren Sie zum Beheben dieses Problems [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).  Diese Version enthält .NET Framework 2.0 \(die Folgeversion von .NET Framework 1.1\), die unter [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] und Windows 10 unterstützt wird.  Sie sollten immer versuchen, zunächst die Anwendung zu installieren, um herauszufinden, ob automatisch eine Aktualisierung auf eine höhere Version von .NET Framework durchgeführt wird.  Wenn dies nicht der Fall ist, wenden Sie sich an den unabhängigen Softwareanbieter um ein Update für die Anwendung zu erhalten.  
  
## Siehe auch  
 [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Installieren von .NET Framework 3.5 auf Windows 8 und höher](../../../docs/framework/install/net-framework-3-5-on-windows-8-plus.md)