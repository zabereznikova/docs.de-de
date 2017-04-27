---
title: "Laufzeitänderungen in .NET Framework 4.5.2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 247fbf574f13985fc941f252c0a6e7268194c079
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-452"></a>Änderungen zur Laufzeit in .NET Framework 4.5.2
In seltenen Fällen können sich Laufzeitänderungen auf Apps auswirken, die frühere Versionen des .NET Frameworks als Ziel verwenden, jedoch in der .NET Framework 4.5.2-Laufzeit ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## <a name="aspnet-runtime-changes"></a>ASP.NET-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|`enableViewStateMac`-Attribut des [pages-Elements](http://msdn.microsoft.com/en-us/4123bb66-3fe4-4d62-b70e-33758656b458)|In ASP.NET sind die folgenden Angaben nicht mehr erlaubt:<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> oder:<br /><br /> `<@Page EnableViewStateMac="false" %>`|Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Es sind nur Apps betroffen, die die <xref:System.Web.UI.Page.EnableViewStateMac%2A>-Eigenschaft explizit auf `false` festlegen.<br /><br /> Weitere Informationen finden Sie unter [Beheben von Fehlern bezüglich des Ansichtszustand-Nachrichtenauthentifizierungscodes (MAC)](http://support.microsoft.com/kb/2915218).|Hauptversion|  
  
<a name="EF"></a>   
## <a name="entity-framework-runtime-changes"></a>Entity Framework-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|-------------|------------|------------|-----------|  
|Beziehungen über eine Abfrageansicht|Entity Framework löst keine <xref:System.StackOverflowException>-Ausnahme mehr aus, wenn eine App eine Abfrage ausführt und dabei eine Abfrageansicht verwendet, die eine 0..1-Navigationseigenschaft verwendet und versucht, die verwandten Entitäten als Teil der Abfrage zu verwenden (z. B. durch Aufrufen von `.Include(e=>e.RelatedNavProp)`).|Diese Änderung betrifft nur Code, der Abfrageansichten mit 1-0..1-Beziehungen verwendet und Abfragen ausführt, die `.Include` aufrufen. Diese Änderung verbessert die Zuverlässigkeit und sollte für beinahe alle Apps transparent sein. Falls jedoch ein unerwünschtes Verhalten auftritt, können Sie dieses Feature deaktivieren, indem Sie den folgenden Eintrag im `<appSettings>`-Bereich der Anwendungskonfigurationsdatei einfügen:<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Kante|  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
