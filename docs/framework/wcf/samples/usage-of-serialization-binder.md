---
title: "Verwendung des Serialisierungsbinders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Verwendung des Serialisierungsbinders
In diesem Beispiel wird gezeigt, wie der <xref:System.Runtime.Serialization.SerializationBinder> verwendet wird, um die Version eines generischen Typs zu ändern, während diese serialisiert wird.  
  
## Veranschaulicht  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## Diskussion  
 In diesem Beispiel wird gezeigt, wie zwei Entitäten, die andere [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Versionen als Ziel haben, mit dem binären Formatierungsprogramm und dem Serialisierungsbinder kommunizieren können.  
  
 Dieses Beispiel wurde mit .NET\-Remoting entwickelt.Das Beispiel besteht aus einem Server mit der Zielversion [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], mit dem ein Vertrag mit generischen Typen implementiert wird, und zwei verschiedene Clients, einer mit der Zielversion [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] und einer mit der Zielversion [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Vom Server wird ein <xref:System.Runtime.Serialization.SerializationBinder> an den binären Formatierungsprogramm angehängt, damit die Versionen der Typen entsprechend bei der Serialisierung geändert werden können. Deshalb können beide Clients diese Typen ordnungsgemäß deserialisieren.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Um den Client auszuführen, klicken Sie mit der rechten Maustaste auf die Projektmappe SBGenericsVTS \(6 Projekte\), und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie unter **Allgemeine Eigenschaften** die Option **Startprojekt** und danach **Mehrere Startprojekte** aus.  
  
3.  Wählen Sie zuerst **Server**, dann **Client20** und dann **Client40** aus.Wählen Sie die Aktion **Start** für diese drei Projekte aus, und lassen Sie den Rest auf **None** festgelegt.  
  
4.  Klicken Sie auf **OK**, und drücken Sie dann F5, um das Beispiel auszuführen.