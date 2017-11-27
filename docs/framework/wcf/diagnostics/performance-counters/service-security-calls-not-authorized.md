---
title: 'Dienst: Security Calls Not Authorized'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5dae370d90082c9efe89f9d523740fc25ece21ab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-calls-not-authorized"></a>Dienst: Security Calls Not Authorized
Indikatorname: Security Calls Not Authorized.  
  
## <a name="description"></a>Beschreibung  
 Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt. Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.
