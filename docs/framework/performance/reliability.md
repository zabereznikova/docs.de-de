---
title: "Zuverlässigkeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd13a09e66c865630b9db3210bbd95bab14cb214
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="reliability"></a>Zuverlässigkeit
Code, der in Serverumgebungen wie SQL Server ausgeführt wird, muss unbedingt vor asynchronen Ausnahmen geschützt werden. Die in diesem Thema dargestellte Zuverlässigkeit ist nicht nur für SQL Server relevant, sondern für jeden Host, der in einer .NET Framework-Umgebung Version 2.0 ausgeführt wird. Da jedoch SQL Server der erste Dienst ist, der die neuen Zuverlässigkeitsfunktionen von Version 2.0 umfassend verwendet, dient es hier als Beispiel.  
  
 In SQL Server ausgeführter Code unterliegt strengeren Richtlinien zur Zuverlässigkeit als andere Serverumgebungen. Dies liegt daran, dass SQL Server ständig am Rand des Ressourcenverbrauchs betrieben wird.  Die Ausnahmen <xref:System.OutOfMemoryException> und <xref:System.Threading.ThreadAbortException> sind für die SQL Server-Umgebung nicht ungewöhnlich. Diese Richtlinien betreffen im Allgemeinen weniger die Zuverlässigkeit, sondern sind vielmehr darauf ausgerichtet, voll vertrauenswürdigen verwalteten Code bei Wiederverwendung auf <xref:System.AppDomain>-Ebene ordnungsgemäß abzubrechen. So hält der Server auf einfache Weise die Konsistenz und Verfügbarkeit aufrecht.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server-Programmierung und Hostschutzattribute](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Beschreibt, wie SQL Server das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut verwendet, um die Ausführung von verwaltetem Code einzuschränken.  
  
 [Empfohlene Vorgehensweisen für die Zuverlässigkeit](../../../docs/framework/performance/reliability-best-practices.md)  
 Enthält Richtlinien zum Schreiben von Code, der die Zuverlässigkeitsanforderungen erfüllt.  
  
 [Eingeschränkte Ausführungsbereiche](../../../docs/framework/performance/constrained-execution-regions.md)  
 Beschreibt die Funktion und das Verhalten von eingeschränkten Ausführungsbereichen (Constrained Execution Regions, CERs).  
  
## <a name="reference"></a>Verweis  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>

