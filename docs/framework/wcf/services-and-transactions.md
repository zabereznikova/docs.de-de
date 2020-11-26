---
title: Dienste und Transaktionen
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: e60f84aafe6c62a657cd3f27c9ccdb6b65186c35
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235908"
---
# <a name="services-and-transactions"></a>Dienste und Transaktionen

Windows Communication Foundation (WCF)-Anwendungen können eine Transaktion innerhalb eines Clients initiieren und die Transaktion innerhalb des Dienst Vorgangs koordinieren. Clients können eine Transaktion initiieren und mehrere Dienstvorgänge aufrufen und sicherstellen, dass für die Dienstvorgänge entweder ein Commit oder ein Rollback als einzelne Einheit ausgeführt wurde.  
  
 Sie können das Transaktionsverhalten im Dienstvertrag aktivieren, indem Sie ein <xref:System.ServiceModel.ServiceBehaviorAttribute> festlegen und die <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>-Eigenschaft und die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft für Dienstvorgänge, die Clienttransaktionen benötigen, festlegen. Der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Parameter legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine unbehandelten Ausnahmen ausgelöst werden. Weitere Informationen zu diesen Attributen finden Sie unter [Service Model Transaction-Attribute](./feature-details/servicemodel-transaction-attributes.md).  
  
 Die Aufgaben (z. B. die Protokollierung von Datenbankupdates), die in den Dienstvorgängen ausgeführt und von einem Ressourcenmanager verwaltet werden, sind Teil der Clienttransaktionen.  
  
 Das folgende Beispiel veranschaulicht die Nutzung der <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribute und <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribute bei der Steuerung des Transaktionsverhalten aufseiten des Dienstes.  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 Sie können Transaktionen und den Transaktions Fluss aktivieren, indem Sie die Client-und Dienst Bindungen so konfigurieren, dass das WS-AtomicTransaction-Protokoll verwendet wird, und das- [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) Element auf festlegen `true` , wie in der folgenden Beispielkonfiguration gezeigt.  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"
          binding="netTcpBinding"
          bindingConfiguration="netTcpBindingWSAT"
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 Clients können eine Transaktion starten, indem Sie <xref:System.Transactions.TransactionScope> erstellen und Dienstvorgänge im Transaktionsumfang aufrufen.  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Transaktionsunterstützung in System.ServiceModel](./feature-details/transactional-support-in-system-servicemodel.md)
- [Transaktionsmodelle](./feature-details/transaction-models.md)
- [WS-Transaktionsfluss](./samples/ws-transaction-flow.md)
