---
title: Integrieren von Enterprise Services-Transaktionskomponenten
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 292573f911459d8a8419e09d81fd1e54dbc6c70b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184741"
---
# <a name="integrating-enterprise-services-transactional-components"></a>Integrieren von Enterprise Services-Transaktionskomponenten

Windows Communication Foundation (WCF) bietet einen automatischen Mechanismus für die Integration mit Enterprise Services (siehe [Integration mit COM+-Anwendungen](integrating-with-com-plus-applications.md)). Möglicherweise benötigen Sie die Flexibilität zur Entwicklung von Diensten, die von Enterprise Services gehostete Transaktionskomponenten intern verwenden. Da die WCF-Transaktionsfunktion auf <xref:System.Transactions> der Infrastruktur basiert, ist der Prozess für die Integration von <xref:System.Transactions> Enterprise Services mit WCF identisch mit dem Prozess für die Angabe der Interoperabilität zwischen und Enterprise Services, wie in [Interoperabilität mit Enterprise Services und COM+-Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85))beschrieben.  
  
 Um das gewünschte Maß an Interoperabilität zwischen der eingehenden übergebenden Transaktion und der COM+-Kontexttransaktion zu erzielen, muss die Dienstimplementierung eine <xref:System.Transactions.TransactionScope>-Instanz erstellen und den entsprechenden Wert der <xref:System.Transactions.EnterpriseServicesInteropOption>-Enumeration verwenden.  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a>Integrieren von Enterprise Services mit einem Dienstvorgang  
 Der folgende Code veranschaulicht einen Vorgang mit zugelassenem Transaktionsfluss, der einen <xref:System.Transactions.TransactionScope> mit der <xref:System.Transactions.EnterpriseServicesInteropOption.Full>-Option erstellt. Die folgenden Bedingungen sind in diesem Szenario gültig:  
  
- Wenn der Client eine Transaktion übergibt, wird der Vorgang, einschließlich des Aufrufs der Enterprise Services-Komponente, innerhalb des Umfangs dieser Transaktion ausgeführt. Mit <xref:System.Transactions.EnterpriseServicesInteropOption.Full> wird sichergestellt, dass die Transaktion mit dem <xref:System.EnterpriseServices>-Kontext synchronisiert wird. Dies bedeutet, dass die Ambient-Transaktion für <xref:System.Transactions> und <xref:System.EnterpriseServices> identisch ist.  
  
- Wenn der Client keine Transaktion übergibt, wird durch Festlegen von <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> auf `true` ein neuer Transaktionsumfang für den Vorgang erstellt. Auf ähnliche Weise wird mit <xref:System.Transactions.EnterpriseServicesInteropOption.Full> sichergestellt, dass die Transaktion des Vorgangs mit der Transaktion übereinstimmt, die innerhalb des Kontexts der <xref:System.EnterpriseServices>-Komponente verwendet wird.  
  
 Alle zusätzlichen Methodenaufrufe treten auch innerhalb des Transaktionsumfangs des gleichen Vorgangs auf.  
  
```csharp
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services
         // component
  
         // Call UpdateOtherCustomerData method on an Enterprise
         // Services component
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 Wenn keine Synchronisierung zwischen der aktuellen Transaktion eines Vorgangs und den Aufrufen für die Transaktionskomponenten von Enterprise Services erforderlich ist, verwenden Sie die <xref:System.Transactions.EnterpriseServicesInteropOption.None>-Option zum Instanziieren der <xref:System.Transactions.TransactionScope>-Instanz.  
  
## <a name="integrating-enterprise-services-with-a-client"></a>Integrieren von Enterprise Services mit einem Client  
 Der folgende Code veranschaulicht Clientcode, der eine <xref:System.Transactions.TransactionScope>-Instanz mit der <xref:System.Transactions.EnterpriseServicesInteropOption.Full>-Einstellung verwendet. In diesem Szenario treten Aufrufe für Dienstvorgänge, die den Transaktionsfluss unterstützen, innerhalb des Umfangs derselben Transaktion auf wie die Aufrufe für Enterprise Services-Komponenten.  
  
```csharp
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services
        // component
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Integration in COM+ Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Integrieren von COM-Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
