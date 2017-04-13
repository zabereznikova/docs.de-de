---
title: "Debuggen auf dem Client | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56f9ad05-ea1b-4ef6-85f2-890f7ed71567
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Debuggen auf dem Client
Um es den Benutzern leichter zu machen, Clientanwendungen für ihren [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienst zu schreiben, kann der Konfigurationsdatei des Diensts das Dienstverhalten [\<serviceDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) hinzugefügt werden.Dieses Verhalten kann zum Veröffentlichen von Hilfeseiten und für die Rückgabe von verwalteten Ausnahmeinformationen in den Details der SOAP\-Fehler, die an den Client zurückgegeben werden, verwendet werden.