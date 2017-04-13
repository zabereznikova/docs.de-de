---
title: "Dienste und Transaktionen | Microsoft Docs"
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
  - "Dienstverträge [WCF], Entwerfen von Diensten und Transaktionen"
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Dienste und Transaktionen
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen können eine Transaktion aus einem Client initiieren und die Transaktion im Dienstvorgang koordinieren.Clients können eine Transaktion initiieren und mehrere Dienstvorgänge aufrufen und sicherstellen, dass für die Dienstvorgänge entweder ein Commit oder ein Rollback als einzelne Einheit ausgeführt wurde.  
  
 Sie können das Transaktionsverhalten im Dienstvertrag aktivieren, indem Sie ein <xref:System.ServiceModel.ServiceBehaviorAttribute> festlegen und die <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>\-Eigenschaft und die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>\-Eigenschaft für Dienstvorgänge, die Clienttransaktionen benötigen, festlegen.Der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>\-Parameter legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine Ausnahmefehler ausgelöst werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu diesen Attributen finden Sie unter [ServiceModel\-Transaktionsattribute](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
 Die Aufgaben \(z. B. die Protokollierung von Datenbankupdates\), die in den Dienstvorgängen ausgeführt und von einem Ressourcenmanager verwaltet werden, sind Teil der Clienttransaktionen.  
  
 Das folgende Beispiel veranschaulicht die Nutzung der <xref:System.ServiceModel.ServiceBehaviorAttribute>\-Attribute und <xref:System.ServiceModel.OperationBehaviorAttribute>\-Attribute bei der Steuerung des Transaktionsverhalten aufseiten des Dienstes.  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 Sie können Transaktionen und Transaktionsflüsse aktivieren, indem Sie die Clientbindungen und Dienstbindungen konfigurieren, um das WS\-AtomicTransaction\-Protokoll zu verwenden, und indem Sie das [\<transactionFlow\>](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)`true-Element auf`  festlegen, wie in der folgenden Beispielkonfiguration dargestellt wird.  
  
```  
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
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## Siehe auch  
 [Transaktionsunterstützung in System.ServiceModel](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)   
 [Transaktionsmodelle](../../../docs/framework/wcf/feature-details/transaction-models.md)   
 [WS\-Transaktionsfluss](../../../docs/framework/wcf/samples/ws-transaction-flow.md)