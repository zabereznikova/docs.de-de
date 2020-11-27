---
title: 'Vorgehensweise: Erstellen eines Transaktionsdiensts'
ms.date: 03/30/2017
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
ms.openlocfilehash: c3d094dbd5822f6025e1cc6c90aab04b61459314
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286291"
---
# <a name="how-to-create-a-transactional-service"></a><span data-ttu-id="3fe15-102">Vorgehensweise: Erstellen eines Transaktionsdiensts</span><span class="sxs-lookup"><span data-stu-id="3fe15-102">How to: Create a Transactional Service</span></span>

<span data-ttu-id="3fe15-103">In diesem Beispiel werden diverse Aspekte der Erstellung eines Transaktionsdiensts und die Nutzung einer von einem Client initiierten Transaktion für die Koordinierung von Dienstvorgängen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3fe15-103">This sample demonstrates various aspects of creating a transactional service and the use of a client-initiated transaction to coordinate service operations.</span></span>  
  
### <a name="creating-a-transactional-service"></a><span data-ttu-id="3fe15-104">Erstellen eines Transaktionsdiensts</span><span class="sxs-lookup"><span data-stu-id="3fe15-104">Creating a transactional service</span></span>  
  
1. <span data-ttu-id="3fe15-105">Erstellen Sie einen Dienstvertrag, und fügen Sie den Vorgängen die gewünschte Einstellung aus der <xref:System.ServiceModel.TransactionFlowOption>-Enumeration hinzu, um die Anforderungen für eingehende Transaktionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3fe15-105">Create a service contract and annotate the operations with the desired setting from the <xref:System.ServiceModel.TransactionFlowOption> enumeration to specify the incoming transaction requirements.</span></span> <span data-ttu-id="3fe15-106">Beachten Sie, dass Sie auch das <xref:System.ServiceModel.TransactionFlowAttribute> auf die zu implementierende Dienstklasse platzieren können.</span><span class="sxs-lookup"><span data-stu-id="3fe15-106">Note that you can also place the <xref:System.ServiceModel.TransactionFlowAttribute> on the service class being implemented.</span></span> <span data-ttu-id="3fe15-107">Hierdurch wird die Einzelimplementierung einer Schnittstelle, die diese Transaktionseinstellungen nutzt, anstelle von allen Implementierungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3fe15-107">This allows for a single implementation of an interface to use these transaction settings, instead of every implementation.</span></span>  
  
    ```csharp
    [ServiceContract]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // Use this to require an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Mandatory)]  
        double Add(double n1, double n2);  
        [OperationContract]  
        // Use this to permit an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        double Subtract(double n1, double n2);  
    }  
    ```  
  
2. <span data-ttu-id="3fe15-108">Erstellen Sie eine Implementierungsklasse, und verwenden Sie <xref:System.ServiceModel.ServiceBehaviorAttribute>, um optional ein <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> und einen <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3fe15-108">Create an implementation class, and use the <xref:System.ServiceModel.ServiceBehaviorAttribute> to optionally specify a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span></span> <span data-ttu-id="3fe15-109">Beachten Sie, dass in vielen Fällen der standardmäßige <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> von 60 Sekunden und die standardmäßige <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> mit dem Wert `Unspecified` angemessen sind.</span><span class="sxs-lookup"><span data-stu-id="3fe15-109">You should note that in many cases, the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> of 60 seconds and the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> of `Unspecified` are appropriate.</span></span> <span data-ttu-id="3fe15-110">Für jeden Vorgang können Sie das <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut nutzen, um festzulegen, ob die innerhalb der Methode durchgeführte Arbeit innerhalb des Umfangs eines Transaktionsumfangs gemäß dem Wert des <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Attributs erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="3fe15-110">For each operation, you can use the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute to specify whether work performed within the method should occur within the scope of a transaction scope according to the value of the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> attribute.</span></span> <span data-ttu-id="3fe15-111">In diesem Fall stimmt die für die `Add`-Methode verwendete Transaktion mit der obligatorischen eingehenden Transaktionen überein, die vom Client kommt, und die für die `Subtract`-Methode verwendete Transaktion entspricht entweder der eingehenden Transaktion, wenn eine solche vom Client übergeben wurde, oder einer neuen implizit oder lokal erstellten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="3fe15-111">In this case, the transaction used for the `Add` method is the same as the mandatory incoming transaction that is flowed from the client, and the transaction used for the `Subtract` method is either the same as the incoming transaction if one was flowed from the client, or a new implicitly and locally created transaction.</span></span>  
  
    ```csharp
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n1} to {n2}");
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n2} from {n1}");
            return n1 - n2;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
            // This is where the transaction provides specific benefit  
            // - changes to the database will be committed only when  
            // the transaction completes.  
        }  
    }  
    ```  
  
3. <span data-ttu-id="3fe15-112">Konfigurieren Sie die Bindungen in der Konfigurationsdatei, wobei Sie angeben, dass der Transaktionskontext übergeben werden sollte, und die dafür zu verwendenden Protokolle festlegen.</span><span class="sxs-lookup"><span data-stu-id="3fe15-112">Configure the bindings in the configuration file, specifying that the transaction context should be flowed, and the protocols to be used to do so.</span></span> <span data-ttu-id="3fe15-113">Weitere Informationen finden Sie unter [Service Model Transaction Configuration](servicemodel-transaction-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="3fe15-113">For more information, see [ServiceModel Transaction Configuration](servicemodel-transaction-configuration.md).</span></span> <span data-ttu-id="3fe15-114">Der Bindungstyp wird im `binding`-Attribut des Endpunktelements angegeben.</span><span class="sxs-lookup"><span data-stu-id="3fe15-114">Specifically, the binding type is specified in the endpoint element’s `binding` attribute.</span></span> <span data-ttu-id="3fe15-115">Das- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Element enthält ein- `bindingConfiguration` Attribut, das auf eine Bindungs Konfiguration mit dem Namen verweist `transactionalOleTransactionsTcpBinding` , wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fe15-115">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element contains a `bindingConfiguration` attribute that references a binding configuration named `transactionalOleTransactionsTcpBinding`, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="3fe15-116">Der Transaktionsfluss wird auf Konfigurationsebene mithilfe des `transactionFlow`-Attributs aktiviert, und das Transaktionsprotokoll wird über das `transactionProtocol`-Attribut angegeben (wie in folgender Konfiguration gezeigt).</span><span class="sxs-lookup"><span data-stu-id="3fe15-116">Transaction flow is enabled at the configuration level by using the `transactionFlow` attribute, and the transaction protocol is specified using the `transactionProtocol` attribute, as shown in the following configuration.</span></span>  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a><span data-ttu-id="3fe15-117">Unterstützung mehrerer Transaktionsprotokolle</span><span class="sxs-lookup"><span data-stu-id="3fe15-117">Supporting multiple transaction protocols</span></span>  
  
1. <span data-ttu-id="3fe15-118">Um eine optimale Leistung zu erzielen, sollten Sie das OleTransactions-Protokoll für Szenarien mit einem Client und einem Dienst verwenden, die mit Windows Communication Foundation (WCF) geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="3fe15-118">For optimal performance, you should use the OleTransactions protocol for scenarios involving a client and service written using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="3fe15-119">Allerdings ist das WS-AtomicTransaction (WS-AT)-Protokoll für Szenarien nützlich, bei denen Interoperabilität mit Protokollstapeln eines Drittanbieters erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3fe15-119">However, the WS-AtomicTransaction (WS-AT) protocol is useful for scenarios when interoperability with third-party protocol stacks is required.</span></span> <span data-ttu-id="3fe15-120">Sie können WCF-Dienste so konfigurieren, dass Sie beide Protokolle akzeptieren, indem Sie mehrere Endpunkte mit entsprechenden Protokoll spezifischen Bindungen bereitstellen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fe15-120">You can configure WCF services to accept both protocols by providing multiple endpoints with appropriate protocol-specific bindings, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="http://localhost:8000/CalcService"  
        binding="wsHttpBinding"  
        bindingConfiguration="transactionalWsatHttpBinding"  
        contract="ICalculator"  
        name="WSAtomicTransaction_endpoint" />  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="3fe15-121">Das Transaktionsprotokoll wird über das `transactionProtocol`-Attribut festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3fe15-121">The transaction protocol is specified using the `transactionProtocol` attribute.</span></span> <span data-ttu-id="3fe15-122">Bei der vom System bereitgestellten `wsHttpBinding` steht dieses Attribut nicht zur Verfügung, da diese Bindung nur das WS-AT-Protokoll nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="3fe15-122">However, this attribute is absent from the system-provided `wsHttpBinding`, because this binding can only use the WS-AT protocol.</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
        <binding name="transactionalWsatHttpBinding"  
          transactionFlow="true" />  
      </wsHttpBinding>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="controlling-the-completion-of-a-transaction"></a><span data-ttu-id="3fe15-123">Kontrolle des Abschlusses einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="3fe15-123">Controlling the completion of a transaction</span></span>  
  
1. <span data-ttu-id="3fe15-124">Standardmäßig vervollständigen WCF-Vorgänge Transaktionen automatisch, wenn keine nicht behandelten Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="3fe15-124">By default, WCF operations automatically complete transactions if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="3fe15-125">Sie können dieses Verhalten ändern, indem Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Eigenschaft und die <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fe15-125">You can modify this behavior by using the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property and the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method.</span></span> <span data-ttu-id="3fe15-126">Wenn es erforderlich ist, dass ein Vorgang innerhalb derselben Transaktion erfolgt wie ein anderer Vorgang (Beispiel: ein Debit- und Kredit-Vorgang), können Sie das automatische Verhalten für den Abschluss deaktivieren, indem Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Eigenschaft auf `false` festlegen (wie in folgendem `Debit`-Vorgangsbeispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="3fe15-126">When an operation is required to occur within the same transaction as another operation (for example, a debit and credit operation), you can disable the autocomplete behavior by setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` as shown in the following `Debit` operation example.</span></span> <span data-ttu-id="3fe15-127">Die Transaktion, die der `Debit`-Vorgang nutzt, wird nicht abgeschlossen, bevor eine Methode mit der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Eigenschaft auf `true` aufgerufen wird (wie in Vorgang `Credit1` gezeigt) oder wenn die <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>-Methode aufgerufen wird, um explizit die Transaktion als abgeschlossen zu kennzeichnen (wie in Vorgang `Credit2` gezeigt).</span><span class="sxs-lookup"><span data-stu-id="3fe15-127">The transaction the `Debit` operation uses is not completed until a method with the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property set to `true` is called, as shown in the operation `Credit1`, or when the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method is called to explicitly mark the transaction as complete, as shown in the operation `Credit2`.</span></span> <span data-ttu-id="3fe15-128">Beachten Sie, dass die beiden Kreditvorgänge zu Illustrationszwecken angeführt werden und dass ein einzelner Kreditvorgang üblicher wäre.</span><span class="sxs-lookup"><span data-stu-id="3fe15-128">Note that the two credit operations are shown for illustration purposes, and that a single credit operation would be more typical.</span></span>  
  
    ```csharp
    [ServiceBehavior]  
    public class CalculatorService : IAccount  
    {  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Debit(double n)  
        {  
            // Perform debit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void Credit1(double n)  
        {  
            // Perform credit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Credit2(double n)  
        {  
            // Perform alternate credit operation  
  
            OperationContext.Current.SetTransactionComplete();  
            return;  
        }  
    }  
    ```  
  
2. <span data-ttu-id="3fe15-129">Zum Zwecke der Transaktionskorrelation erfordert ein Festlegen der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Eigenschaft auf `false` die Verwendung einer sitzungsbasierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="3fe15-129">For the purposes of transaction correlation, setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` requires the use of a sessionful binding.</span></span> <span data-ttu-id="3fe15-130">Die Anforderung wird mit der `SessionMode`-Eigenschaft auf <xref:System.ServiceModel.ServiceContractAttribute> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3fe15-130">This requirement is specified with the `SessionMode` property on the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span>  
  
    ```csharp
    [ServiceContract(SessionMode = SessionMode.Required)]  
    public interface IAccount  
    {  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Debit(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit1(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit2(double n);  
    }  
    ```  
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a><span data-ttu-id="3fe15-131">Kontrolle der Lebensdauer einer Transaktionsdienstinstanz</span><span class="sxs-lookup"><span data-stu-id="3fe15-131">Controlling the lifetime of a transactional service instance</span></span>  
  
1. <span data-ttu-id="3fe15-132">WCF verwendet die- <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> Eigenschaft, um anzugeben, ob die zugrunde liegende Dienst Instanz freigegeben wird, wenn eine Transaktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3fe15-132">WCF uses the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to specify whether the underlying service instance is released when a transaction completes.</span></span> <span data-ttu-id="3fe15-133">Da standardmäßig auf eingestellt `true` ist, zeigt WCF ein effizientes und vorhersagbares "Just-in-Time"-Aktivierungs Verhalten an, sofern nicht anders konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3fe15-133">Since this defaults to `true`, unless configured otherwise, WCF exhibits an efficient and predictable "just-in-time" activation behavior.</span></span> <span data-ttu-id="3fe15-134">Aufrufe an einen Dienst bei einer nachfolgenden Transaktion erhalten ohne Auswirkung des Status der vorherigen Transaktion garantiert eine neue Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="3fe15-134">Calls to a service on a subsequent transaction are assured a new service instance with no remnants of the previous transaction's state.</span></span> <span data-ttu-id="3fe15-135">Obwohl dies oft nützlich sein kann, möchten Sie eventuell den Status innerhalb der Dienstinstanz bis über den Transaktionsabschluss hinaus beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3fe15-135">While this is often useful, sometimes you may want to maintain state within the service instance beyond the transaction completion.</span></span> <span data-ttu-id="3fe15-136">Beispielsweise könnte dies der Fall sein, wenn erforderliche Status oder Handle zu Ressourcen in der Anschaffung oder Wiederherstellung teuer sind.</span><span class="sxs-lookup"><span data-stu-id="3fe15-136">Examples of this would be when required state or handles to resources are expensive to retrieve or reconstitute.</span></span> <span data-ttu-id="3fe15-137">Sie können dies vornehmen, indem Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A>-Eigenschaft auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3fe15-137">You can do this by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to `false`.</span></span> <span data-ttu-id="3fe15-138">Mit dieser Einstellung stehen die Instanz und alle zugehörigen Status bei folgenden Aufrufen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3fe15-138">With that setting, the instance and any associated state will be available on subsequent calls.</span></span> <span data-ttu-id="3fe15-139">Achten Sie hierbei insbesondere darauf, wann und wie der Zustand und die Transaktion gelöscht und abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3fe15-139">When using this, give careful consideration to when and how state and transactions will be cleared and completed.</span></span> <span data-ttu-id="3fe15-140">Das folgende Beispiel veranschaulicht die Vorgehensweise, indem die Instanz mit der `runningTotal`-Variablen beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3fe15-140">The following sample demonstrates how to do this by maintaining the instance with the `runningTotal` variable.</span></span>  
  
    ```csharp
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n} to {runningTotal}");
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n} from {runningTotal}");
            runningTotal = runningTotal - n;  
            return runningTotal;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
        }  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="3fe15-141">Da die Lebensdauer der Instanz ein dienstinternes Verhalten ist und durch die <xref:System.ServiceModel.ServiceBehaviorAttribute>-Eigenschaft kontrolliert wird, sind keine Änderungen an der Dienstkonfiguration oder am Dienstvertrag erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3fe15-141">Since the instance lifetime is a behavior that is internal to the service, and controlled through the <xref:System.ServiceModel.ServiceBehaviorAttribute> property, no modification to the service configuration or service contract is required to set the instance behavior.</span></span> <span data-ttu-id="3fe15-142">Darüber hinaus enthält die Übertragung keine Darstellung hierzu.</span><span class="sxs-lookup"><span data-stu-id="3fe15-142">In addition, the wire will contain no representation of this.</span></span>
