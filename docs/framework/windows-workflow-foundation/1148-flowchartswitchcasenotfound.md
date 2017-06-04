---
title: "1148 - FlowchartSwitchCaseNotFound | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1148 - FlowchartSwitchCaseNotFound
## Eigenschaften  
  
|||  
|-|-|  
|ID|1148|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass bei einem Flussdiagrammwechsel weder ein übereinstimmender noch ein Standardfall gefunden wurden.  Die Ausführung des Flussdiagramms wird beendet.  
  
## Meldung  
 Flussdiagramm '%1'\/FlowSwitch \- Es wurde weder eine Case\-Aktivität noch ein Standardfall gefunden, der dem Ergebnis des Ausdrucks entspricht.  Die Ausführung des Flussdiagramms wird beendet.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|FlowChart|xs:string|Der Anzeigename des FlowChart.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|