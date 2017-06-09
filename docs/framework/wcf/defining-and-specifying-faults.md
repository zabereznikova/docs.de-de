---
title: "Definieren und Angeben von Fehlern | Microsoft Docs"
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
  - "Behandeln von Fehlern [WCF], Definieren"
  - "Behandeln von Fehlern [WCF], Angeben"
ms.assetid: c00c84f1-962d-46a7-b07f-ebc4f80fbfc1
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Definieren und Angeben von Fehlern
SOAP\-Fehler vermitteln Informationen zu Fehlerbedingungen auf interoperable Weise von einem Dienst an einen Client und bei Duplexkommunikation von einem Client an einen Dienst.  In diesem Thema wird beschrieben, wann und wie Sie benutzerdefinierten Fehlerinhalt definieren und wie Sie angeben, welche Vorgänge diesen zurückgeben können.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] dazu, wie ein Dienst oder ein Duplexclient diese Fehler senden kann und wie eine Client\- oder Dienstanwendung diese Fehler verarbeitet, finden Sie unter [Senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md).  Eine Übersicht über die Fehlerbehandlung bei [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## Übersicht  
 Bei deklarierten SOAP\-Fehlern verfügt ein Vorgang über ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>, das einen benutzerdefinierten SOAP\-Fehlertyp angibt.  Nicht deklarierte SOAP\-Fehler sind Fehler, die nicht im Vertrag eines Vorgangs festgelegt sind.  Dieses Thema enthält Informationen zur Identifizierung der Fehlerbedingungen und zur Erstellung eines Fehlervertrags für Ihren Dienst, den Clients verwenden können, um die Fehlerbedingungen richtig zu verarbeiten, wenn sie anhand von benutzerdefinierten SOAP\-Fehlern darüber informiert werden.  Die folgenden grundlegenden Aufgaben gelten in dieser Reihenfolge:  
  
1.  Definieren Sie die Fehlerbedingungen, über die ein Client Ihres Dienstes informiert werden sollte.  
  
2.  Definieren Sie für diese Fehlerbedingungen den benutzerdefinierten Inhalt der SOAP\-Fehler.  
  
3.  Kennzeichnen Sie Ihre Vorgänge, damit die spezifischen SOAP\-Fehler, die diese Vorgänge auslösen, für Clients in WSDL offengelegt werden.  
  
### Definieren von Fehlerbedingungen, über die Clients informiert werden sollen  
 SOAP\-Fehler sind öffentlich beschriebene Meldungen, die Fehlerinformationen für einen besonderen Vorgang enthalten.  Da sie zusammen mit anderen Vorgangsmeldungen in WSDL beschrieben sind, sind Clients darüber informiert und erwarten beim Aufrufen eines Vorgangs, dass sie diese ggf. verarbeiten müssen.  Da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste jedoch in verwaltetem Code geschrieben sind, ermöglicht es Ihnen die Entscheidung, welche Fehlerbedingungen in verwaltetem Code in Fehler konvertiert und an den Client zurückgegeben werden, Fehlerbedingungen und Fehler in Ihrem Dienst von der formalen Fehlerkonversation mit einem Client zu trennen.  
  
 Das folgende Codebeispiel zeigt zum Beispiel einen Vorgang, bei dem zwei ganze Zahlen verwendet und eine weitere ganze Zahl zurückgegeben wird.  Hierbei können mehrere Ausnahmen ausgelöst werden. Beim Entwerfen des Fehlervertrags müssen Sie deshalb bestimmen, welche Fehlerbedingungen für Ihren Client wichtig sind.  In diesem Fall muss der Dienst die <xref:System.DivideByZeroException?displayProperty=fullName>\-Ausnahme erkennen.  
  
```csharp  
[ServiceContract]  
public class CalculatorService  
{  
    [OperationContract]   
    int Divide(int a, int b)  
    {  
      if (b==0) throw new Exception("Division by zero!");  
      return a/b;  
    }  
}  
```  
  
```vb  
<ServiceContract> _  
Public Class CalculatorService  
    <OperationContract]> _  
    Public Function Divide(ByVal a As Integer, ByVal b As Integer) _  
       As Integer  
      If (b==0) Then   
            Throw New Exception("Division by zero!")  
      Return a/b  
    End Function  
End Class  
```  
  
 Im obigen Beispiel kann der Vorgang entweder einen benutzerdefinierten SOAP\-Fehler zurückgeben, der für die Division durch 0 gilt, einen benutzerdefinierten Fehler, der für mathematische Operationen gilt, aber Informationen zur Division durch 0 enthält, mehrere Fehler für verschiedene Fehlersituationen oder keinen SOAP\-Fehler.  
  
### Definieren des Inhalts von Fehlerbedingungen  
 Nachdem eine Fehlerbedingung als Bedingung identifiziert wurde, die auf nützliche Weise einen benutzerdefinierten SOAP\-Fehler zurückgeben kann, besteht der nächste Schritt darin, den Inhalt dieses Fehlers zu definieren und sicherzustellen, dass die Inhaltsstruktur serialisiert werden kann.  Das Codebeispiel im vorherigen Abschnitt zeigt einen Fehler, der spezifisch für eine `Divide`\-Operation ist. Wenn jedoch auch noch andere Operationen über den `Calculator`\-Dienst durchgeführt werden, kann ein einzelner benutzerdefinierter SOAP\-Fehler den Client über alle Rechnerfehlerbedingungen informieren, einschließlich `Divide`.  Das folgende Codebeispiel zeigt die Erstellung des benutzerdefinierten SOAP\-Fehlers `MathFault`. Dieser Fehler kann Fehler für alle mathematischen Operationen melden, auch für `Divide`.  Während die Klasse eine Operation \(die `Operation`\-Eigenschaft\) und einen Wert angeben kann, der das Problem beschreibt \(die `ProblemType`\-Eigenschaft\), müssen die Klasse und diese Eigenschaften serialisierbar sein, um per benutzerdefiniertem SOAP\-Fehler an den Client übertragen zu werden.  Aus diesem Grund werden die Attribute <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=fullName> und <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=fullName> verwendet, um den Typ und seine Eigenschaften serialisierbar und so interoperabel wie möglich zu machen.  
  
 [!code-csharp[Faults#2](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#2)]
 [!code-vb[Faults#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#2)]  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Sicherstellen der Serialisierbarkeit der Daten finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).  Eine Liste der Serialisierungsunterstützung, die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> bereitstellt, finden Sie unter [Vom Datenvertragsserialisierer unterstützte Typen](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
### Markieren von Operationen, um den Fehlervertrag einzurichten  
 Nachdem Sie eine serialisierbare Datenstruktur definiert haben, die als Teil eines benutzerdefinierten SOAP\-Fehlers zurückgegeben wird, besteht der letzte Schritt darin, Ihren Operationsvertrag so zu kennzeichnen, dass er einen SOAP\-Fehler dieses Typs auslöst.  Verwenden Sie dazu das <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>\-Attribut, und übergeben Sie den Typ des benutzerdefinierten Datentyps, den Sie erstellt haben.  Das folgende Codebeispiel zeigt, wie Sie das <xref:System.ServiceModel.FaultContractAttribute>\-Attribut verwenden, um anzugeben, dass die `Divide`\-Operation einen SOAP\-Fehler vom Typ `MathFault` zurückgeben kann.  Andere mathematische Operationen können jetzt auch angeben, dass sie einen `MathFault` zurückgeben können.  
  
 [!code-csharp[Faults#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#1)]
 [!code-vb[Faults#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#1)]  
  
 Eine Operation kann angeben, dass sie mehr als einen benutzerdefinierten Fehler zurückgibt, indem Sie diese mit mehr als einem <xref:System.ServiceModel.FaultContractAttribute>\-Attribut versehen.  
  
 Der nächste Schritt, das Einrichten des Fehlervertrags in der Implementierung der Operation, ist im Thema [Senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md) beschrieben.  
  
#### Überlegungen zu SOAP, WSDL und zur Interoperabilität  
 Unter bestimmten Umständen, besonders bei der Zusammenarbeit mit anderen Plattformen, kann es wichtig sein, die Art und Weise der Anzeige eines Fehlers in einer SOAP\-Meldung bzw. seine Beschreibung in WSDL\-Metadaten zu steuern.  
  
 Das <xref:System.ServiceModel.FaultContractAttribute>\-Attribut verfügt über eine <xref:System.ServiceModel.FaultContractAttribute.Name%2A>\-Eigenschaft, die die Steuerung des WSDL\-Fehlerelementnamens ermöglicht, der in den Metadaten für diesen Fehler generiert wird.  
  
 Gemäß SOAP\-Standard kann ein Fehler die Elemente `Action`, `Code` und `Reason` aufweisen.  Die `Action` wird von der <xref:System.ServiceModel.FaultContractAttribute.Action%2A>\-Eigenschaft gesteuert.  Die <xref:System.ServiceModel.FaultException.Code%2A>\-Eigenschaft und die <xref:System.ServiceModel.FaultException.Reason%2A>\-Eigenschaften sind Eigenschaften der <xref:System.ServiceModel.FaultException?displayProperty=fullName>\-Klasse, bei der es sich um die übergeordnete Klasse der generischen <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> handelt.  Die `Code`\-Eigenschaft enthält einen <xref:System.ServiceModel.FaultCode.SubCode%2A>\-Member.  
  
 Beim Zugreifen auf andere Elemente als Dienste, die Fehler generieren, gelten bestimmte Einschränkungen.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] unterstützt nur Fehler mit Detailtypen, die das Schema beschreibt und die mit Datenverträgen kompatibel sind.  Wie oben erwähnt, unterstützt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] zum Beispiel keine Fehler, die in ihren Detailtypen XML\-Attribute verwenden, und keine Fehler mit mehr als einem Element der obersten Ebene im Detailabschnitt.  
  
## Siehe auch  
 <xref:System.ServiceModel.FaultContractAttribute>   
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)   
 [Senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md)   
 [Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)   
 [Grundlagen der Schutzebene](../../../docs/framework/wcf/understanding-protection-level.md)   
 [Vorgehensweise: Festlegen der ProtectionLevel\-Eigenschaft](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)   
 [Angeben von Datenübertragung in Dienstverträgen](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)