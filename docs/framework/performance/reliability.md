---
title: Zuverlässigkeit
description: Verstehen der Zuverlässigkeit in .net. Schutz vor asynchronen Ausnahmen in Hosts, die in .NET ausgeführt werden, z. b. SQL Server.
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
ms.openlocfilehash: ce9ffbb7f58c2f5dc016c56c0e2ce13b45c30f26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474253"
---
# <a name="reliability"></a>Zuverlässigkeit
Code, der in Serverumgebungen wie SQL Server ausgeführt wird, muss unbedingt vor asynchronen Ausnahmen geschützt werden. Die in diesem Thema dargestellte Zuverlässigkeit ist nicht nur für SQL Server relevant, sondern für jeden Host, der in einer .NET Framework-Umgebung Version 2.0 ausgeführt wird. Da jedoch SQL Server der erste Dienst ist, der die neuen Zuverlässigkeitsfunktionen von Version 2.0 umfassend verwendet, dient es hier als Beispiel.  
  
 In SQL Server ausgeführter Code unterliegt strengeren Richtlinien zur Zuverlässigkeit als andere Serverumgebungen. Dies liegt daran, dass SQL Server ständig am Rand des Ressourcenverbrauchs betrieben wird.  Die Ausnahmen <xref:System.OutOfMemoryException> und <xref:System.Threading.ThreadAbortException> sind für die SQL Server-Umgebung nicht ungewöhnlich. Diese Richtlinien betreffen im Allgemeinen weniger die Zuverlässigkeit, sondern sind vielmehr darauf ausgerichtet, voll vertrauenswürdigen verwalteten Code bei Wiederverwendung auf <xref:System.AppDomain>-Ebene ordnungsgemäß abzubrechen. So hält der Server auf einfache Weise die Konsistenz und Verfügbarkeit aufrecht.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server-Programmierung und Hostschutzattribute](sql-server-programming-and-host-protection-attributes.md)  
 Beschreibt, wie SQL Server das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut verwendet, um die Ausführung von verwaltetem Code einzuschränken.  
  
 [Empfohlene Vorgehensweisen für die Zuverlässigkeit](reliability-best-practices.md)  
 Enthält Richtlinien zum Schreiben von Code, der die Zuverlässigkeitsanforderungen erfüllt.  
  
 [Eingeschränkte Ausführungsbereiche (CERs)](constrained-execution-regions.md)  
 Beschreibt die Funktion und das Verhalten von eingeschränkten Ausführungsbereichen (Constrained Execution Regions, CERs).  
  
## <a name="reference"></a>Referenz  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
