---
title: "Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ProtectionLevel-Eigenschaft"
  - "WCF, Sicherheit"
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft
Sie können die Schutzebene festlegen, indem Sie ein entsprechendes Attribut anwenden und die Eigenschaft einrichten.Sie können den Schutz auf Dienstebene einrichten, um alle Teile einer Nachricht anzupassen. Darüber hinaus können Sie den Schutz auf stärker unterteilten Ebenen einrichten – von den Methoden zu den Nachrichtenteilen.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zur `ProtectionLevel`\-Eigenschaft finden Sie unter [Grundlagen der Schutzebene](../../../docs/framework/wcf/understanding-protection-level.md).  
  
> [!NOTE]
>  Schutzebenen können nur im Code, nicht in der Konfiguration festgelegt werden.  
  
### So signieren Sie alle Nachrichten für einen Dienst  
  
1.  Erstellen Sie eine Schnittstelle für den Dienst.  
  
2.  Wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut für den Dienst an, und legen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel> fest. Dies wird im folgenden Code veranschaulicht \(die Standardebene ist <xref:System.Net.Security.ProtectionLevel>\).  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### So signieren Sie alle Nachrichtenteile für einen Vorgang  
  
1.  Erstellen Sie eine Schnittstelle für den Dienst, und wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut auf die Schnittstelle an.  
  
2.  Fügen Sie der Schnittstelle eine Methodendeklaration hinzu.  
  
3.  Wenden Sie das <xref:System.ServiceModel.OperationContractAttribute>\-Attribut auf die Methode an, und setzen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel>. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## Schützen von Fehlernachrichten  
 Ausnahmen, die auf einem Dienst ausgelöst werden, können auf einem Client als SOAP\-Fehler eingerichtet werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Erstellen stark typisierter Fehler finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) und [Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).  
  
#### So schützen Sie eine Fehlernachricht  
  
1.  Erstellen Sie einen Typ, der die Fehlernachricht darstellt.Das folgende Beispiel erstellt eine Klasse mit dem Namen `MathFault` und zwei Feldern.  
  
2.  Wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut auf den Typ und das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut für jedes Feld an, das serialisiert werden soll. Der folgende Code veranschaulicht dies.  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3.  Wenden Sie in der Schnittstelle, die den Fehler zurückgibt, das <xref:System.ServiceModel.FaultContractAttribute>\-Attribut auf die Methode an, die den Fehler zurückgibt, und setzen Sie den `detailType`\-Parameter auf den Typ der Fehlerklasse.  
  
4.  Setzen Sie ebenfalls im Konstruktor die <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A>\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel>. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## Schützen von Nachrichtenteilen  
 Verwenden Sie einen Nachrichtenvertrag, um Teile einer Nachricht zu schützen.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Nachrichtenverträgen finden Sie unter [Verwendung von Nachrichtenverträgen](../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
#### So schützen Sie einen Nachrichtentext  
  
1.  Erstellen Sie einen Typ, der die Nachricht darstellt.Das folgende Beispiel erstellt eine `Company`\-Klasse mit zwei Feldern, `CompanyName` und `CompanyID`.  
  
2.  Wenden Sie das <xref:System.ServiceModel.MessageContractAttribute>\-Attribut auf die Klasse an, und setzen Sie die <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A>\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel>.  
  
3.  Wenden Sie das <xref:System.ServiceModel.MessageHeaderAttribute>\-Attribut auf ein Feld an, das als Nachrichtenheader ausgedrückt wird, und setzen Sie die `ProtectionLevel`\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel>.  
  
4.  Wenden Sie <xref:System.ServiceModel.MessageBodyMemberAttribute> auf jegliches Feld an, das als Teil des Nachrichtentexts ausgedrückt wird, und setzen Sie die `ProtectionLevel`\-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel>. Dies wird im folgenden Beispiel veranschaulicht.  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `ProtectionLevel`\-Eigenschaft mehrerer Attributklassen an verschiedenen Stellen in einem Dienst festgelegt.  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## Kompilieren des Codes  
 Der folgende Code zeigt die für die Kompilierung des Beispielcodes erforderlichen Namespaces.  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>   
 <xref:System.ServiceModel.FaultContractAttribute>   
 <xref:System.ServiceModel.MessageContractAttribute>   
 <xref:System.ServiceModel.MessageBodyMemberAttribute>   
 [Grundlagen der Schutzebene](../../../docs/framework/wcf/understanding-protection-level.md)