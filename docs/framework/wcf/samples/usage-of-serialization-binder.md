---
title: Verwendung des Serialisierungsbinders
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77f5c2914051c4310102a57b7181333bab6811b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-serialization-binder"></a>Verwendung des Serialisierungsbinders
In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie zwei Entitäten, die andere [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen als Ziel haben, mit dem binären Formatierungsprogramm und dem Serialisierungsbinder kommunizieren können.  
  
 Dieses Beispiel wurde mit .NET-Remoting entwickelt. Das Beispiel besteht aus einem Server mit der Zielversion [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], mit dem ein Vertrag mit generischen Typen implementiert wird, und zwei verschiedene Clients, einer mit der Zielversion [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Um den Client auszuführen, Maustaste die Projektmappe SBGenericsVTS (6 Projekte), und wählen Sie dann **Eigenschaften**.  
  
2.  In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie dann **mehrere Startprojekte**.  
  
3.  Wählen Sie **Server** zuerst, dann **Client20** und dann **Client40**. Wählen Sie die **starten** Aktion für diese drei Projekte, und behalten Sie die restlichen festgelegt **keine**.  
  
4.  Klicken Sie auf **OK** und drücken Sie F5, um das Beispiel ausführen.
