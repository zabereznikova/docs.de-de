---
title: 'Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 359364228c4ab4d5b247f4f42f3ef3391f774197
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236597"
---
# <a name="how-to-set-the-protectionlevel-property"></a>Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft

Sie können die Schutzebene festlegen, indem Sie ein entsprechendes Attribut anwenden und die Eigenschaft einrichten. Sie können den Schutz auf Dienstebene einrichten, um alle Teile einer Nachricht anzupassen. Darüber hinaus können Sie den Schutz auf stärker unterteilten Ebenen einrichten – von den Methoden zu den Nachrichtenteilen. Weitere Informationen zur- `ProtectionLevel` Eigenschaft finden Sie Untergrund Legendes zu [Schutz Ebenen](understanding-protection-level.md).  
  
> [!NOTE]
> Schutzebenen können nur im Code, nicht in der Konfiguration festgelegt werden.  
  
### <a name="to-sign-all-messages-for-a-service"></a>So signieren Sie alle Nachrichten für einen Dienst  
  
1. Erstellen Sie eine Schnittstelle für den Dienst.  
  
2. Wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut für den Dienst an, und legen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.Sign> fest. Dies wird im folgenden Code veranschaulicht (die Standardebene ist <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a>So signieren Sie alle Nachrichtenteile für einen Vorgang  
  
1. Erstellen Sie eine Schnittstelle für den Dienst, und wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut auf die Schnittstelle an.  
  
2. Fügen Sie der Schnittstelle eine Methodendeklaration hinzu.  
  
3. Wenden Sie das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die Methode an, und setzen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.Sign>. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a>Schützen von Fehlernachrichten  

 Ausnahmen, die für einen Dienst ausgelöst werden, können als SOAP-Fehler an einen Client gesendet werden. Weitere Informationen zum Erstellen stark typisierter Fehler finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md) und Gewusst [wie: Deklarieren von Fehlern in Dienstverträgen](how-to-declare-faults-in-service-contracts.md).  
  
#### <a name="to-protect-a-fault-message"></a>So schützen Sie eine Fehlernachricht  
  
1. Erstellen Sie einen Typ, der die Fehlernachricht darstellt. Das folgende Beispiel erstellt eine Klasse mit dem Namen `MathFault` und zwei Feldern.  
  
2. Wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf den Typ und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut für jedes Feld an, das serialisiert werden soll. Der folgende Code veranschaulicht dies.  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. Wenden Sie in der Schnittstelle, die den Fehler zurückgibt, das <xref:System.ServiceModel.FaultContractAttribute>-Attribut auf die Methode an, die den Fehler zurückgibt, und setzen Sie den `detailType`-Parameter auf den Typ der Fehlerklasse.  
  
4. Setzen Sie ebenfalls im Konstruktor die <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a>Schützen von Nachrichtenteilen  

 Verwenden Sie einen Nachrichtenvertrag, um Teile einer Nachricht zu schützen. Weitere Informationen zu Nachrichten Verträgen finden Sie unter [Verwenden von Nachrichten Verträgen](./feature-details/using-message-contracts.md).  
  
#### <a name="to-protect-a-message-body"></a>So schützen Sie einen Nachrichtentext  
  
1. Erstellen Sie einen Typ, der die Nachricht darstellt. Das folgende Beispiel erstellt eine `Company`-Klasse mit zwei Feldern, `CompanyName` und `CompanyID`.  
  
2. Wenden Sie das <xref:System.ServiceModel.MessageContractAttribute>-Attribut auf die Klasse an, und setzen Sie die <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
3. Wenden Sie das <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut auf ein Feld an, das als Nachrichtenheader ausgedrückt wird, und setzen Sie die `ProtectionLevel`-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
4. Wenden <xref:System.ServiceModel.MessageBodyMemberAttribute> Sie auf ein beliebiges Feld an, das als Teil des Nachrichten Texts ausgedrückt wird, und legen Sie die- `ProtectionLevel` Eigenschaft auf fest <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> , wie im folgenden Beispiel gezeigt.  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die `ProtectionLevel`-Eigenschaft mehrerer Attributklassen an verschiedenen Stellen in einem Dienst festgelegt.  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Der folgende Code zeigt die für die Kompilierung des Beispielcodes erforderlichen Namespaces.  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [Grundlagen der Schutzebene](understanding-protection-level.md)
