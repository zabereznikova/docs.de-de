---
title: "Kernkommunikationen: Webhost-Unterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Kernkommunikationen: Webhost-Unterst&#252;tzung
In diesem Thema werden alle Ausnahmen aufgelistet, die von der Webhost\-Unterstützung generiert werden.  
  
## Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|--------------------|----------------------------|  
|Hosting\_CompatibilityServiceNotHosted|Dieser Dienst erfordert ASP.NET\-Kompatibilität.Er muss außerdem in IIS gehostet werden.Hosten Sie den Dienst entweder in ISS mit aktivierter ASP.NET\-Kompatibilität in der Web.config\-Datei, oder legen Sie die AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode\-Eigenschaft auf einen anderen Wert als "Erforderlich" fest.|  
|Hosting\_ListenerNotFoundForActivationInRecycling|Kein Kanal führt an der angegebenen Adresse aktiv eine Überwachung aus.Wenn eine Anwendung wiederverwendet wird, wird der Dienst geschlossen.|  
|Hosting\_NonHTTPInCompatibilityMode|Die einzigen Protokolle, die unter ASP.NET\-Kompatibilität unterstützt werden, sind HTTP und HTTPS.Entfernen Sie den angegebenen Endpunkt, oder deaktivieren Sie ASP.NET\-Kompatibilität für die Anwendung.|  
|Hosting\_ProcessNotExecutingUnderHostedContext|Der angegebene Hosting\-Prozess kann innerhalb der aktuellen Hostumgebung nicht aufgerufen werden.Diese API erfordert, dass die aufrufende Anwendung in Internet Information Services \(IIS\) oder Windows Process Activation Service \(WAS\) gehostet wird.|  
|Hosting\_ServiceCompatibilityRequire|Der Dienst kann nicht aktiviert werden, da er ASP.NET\-Kompatibilität erfordert.ASP.NET\-Kompatibilität ist für diese Anwendung nicht aktiviert.Aktivieren Sie entweder ASP.NET\-Kompatibilität in der Web.config\-Datei, oder legen Sie die AspNetCompatibilityRequirementsAttribute.AspNetCompatibility\-Eigenschaft fest.|