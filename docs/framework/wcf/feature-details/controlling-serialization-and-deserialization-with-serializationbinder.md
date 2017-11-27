---
title: Steuern der Serialisierung und Deserialisierung mit SerializationBinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c3180d62824f94e27e02c80e09fdf32252f0a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Steuern der Serialisierung und Deserialisierung mit SerializationBinder
Ein Formatierungsprogramm überträgt während der Serialisierung die Informationen, die zum Erstellen einer Instanz eines Objekts mit dem korrekten Typ und der korrekten Version erforderlich sind. Diese Informationen enthalten i. d. R. den vollständigen Typ- und Assemblynamen des Objekts. Standardmäßig verwendet die Deserialisierung diese Informationen zum Erstellen einer Instanz eines identischen Objekts. Einige Benutzer müssen ggf. steuern, welche Klasse serialisiert und deserialisiert werden soll. Der Grund dafür kann sein, dass die ursprüngliche Klasse auf dem Computer, der die Deserialisierung ausführt, nicht vorhanden ist, dass die ursprüngliche Klasse die Assembly gewechselt hat oder dass auf dem Server und Client eine andere Version der Klasse erforderlich ist. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwendung des Serialisierungsbinders](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Die Funktion ist nur verfügbar, wenn Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> oder <xref:System.Runtime.Serialization.NetDataContractSerializer> verwenden.  
  
## <a name="using-serializationbinder"></a>Verwenden von SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden. Leiten Sie zum Steuern der Serialisierung oder Deserialisierung verwendeten bekannten Typen eine Klasse von <xref:System.Runtime.Serialization.SerializationBinder> und überschreiben die <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String "," System.String)?qualifyHint=False "und" AutoUpgrade = "true" und <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)? QualifyHint = "false" & AutoUpgrade = "true" Methoden. Die <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String "," System.String)?qualifyHint=False "und" AutoUpgrade = "true"-Methode übernimmt ein <xref:System.Type> und gibt den Namen einer Assembly und Typ. Die <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False & AutoUpgrade = "true"-Methode akzeptiert eine Assembly und Typnamen und gibt eine <xref:System.Type>.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Verwendung des Serialisierungsbinders](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
