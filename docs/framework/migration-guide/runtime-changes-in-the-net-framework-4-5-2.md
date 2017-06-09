---
title: "&#196;nderungen zur Laufzeit in .NET Framework 4.5.2 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# &#196;nderungen zur Laufzeit in .NET Framework 4.5.2
In seltenen Fällen können sich Laufzeitänderungen auf Apps auswirken, die frühere Versionen des .NET Frameworks als Ziel verwenden, jedoch in der .NET Framework 4.5.2\-Laufzeit ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## ASP.NET\-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|`enableViewStateMac`\-Attribut des [pages\-Elements](http://msdn.microsoft.com/de-de/4123bb66-3fe4-4d62-b70e-33758656b458)|In ASP.NET sind die folgenden Angaben nicht mehr erlaubt:<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> oder:<br /><br /> `<@Page EnableViewStateMac="false" %>`|Der Nachrichtenauthentifizierungscode \(MAC\) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Nur Apps, die die <xref:System.Web.UI.Page.EnableViewStateMac%2A>\-Eigenschaft explizit auf `false` setzen, sind betroffen.<br /><br /> Weitere Informationen finden Sie unter [Beheben von Fehlern bezüglich des Ansichtszustand\-Nachrichtenauthentifizierungscodes \(MAC\)](http://support.microsoft.com/kb/2915218).|Hauptversion|  
  
<a name="EF"></a>   
## Entity Framework\-Laufzeitänderungen  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|Beziehungen über eine Abfrageansicht|Entity Framework löst keine <xref:System.StackOverflowException>\-Ausnahme mehr aus, wenn eine App eine Abfrage ausführt und dabei eine Abfrageansicht verwendet, die eine 0..1\-Navigationseigenschaft verwendet und versucht, die verwandten Entitäten als Teil der Abfrage zu verwenden \(z. B. durch Aufrufen von `.Include(e=>e.RelatedNavProp)`\).|Diese Änderung betrifft nur Code, der Abfrageansichten mit 1\-0..1\-Beziehungen verwendet und Abfragen ausführt, die `.Include` aufrufen. Diese Änderung verbessert die Zuverlässigkeit und sollte für beinahe alle Apps transparent sein. Falls jedoch ein unerwünschtes Verhalten auftritt, können Sie dieses Feature deaktivieren, indem Sie den folgenden Eintrag im `<appSettings>`\-Bereich der Anwendungskonfigurationsdatei einfügen:<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Kante|  
  
## Siehe auch  
 [Neuzuweisung von Änderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)