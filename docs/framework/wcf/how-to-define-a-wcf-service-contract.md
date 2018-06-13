---
title: 'Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5e8abbf8c5f9b0696d90ccbee94c5d8f4dd8b1ec
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809224"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags
Dies ist die erste von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.  
  
 Wenn Sie einen WCF-Dienst zu erstellen, ist die erste Aufgabe zum Definieren eines Dienstvertrags. Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt. Ein Vorgang ähnelt einer Webdienstmethode. Verträge werden durch Definieren einer C++-, einer C#- oder einer Visual Basic (VB)-Schnittstelle erstellt. Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang. Auf jede Schnittstelle muss das <xref:System.ServiceModel.ServiceContractAttribute> angewendet werden, und auf jeden Vorgang muss das <xref:System.ServiceModel.OperationContractAttribute> angewendet werden. Wenn eine Methode in einer Schnittstelle, die über das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut verfügt, nicht das <xref:System.ServiceModel.OperationContractAttribute>-Attribut aufweist, wird diese Methode vom Dienst nicht verfügbar gemacht.  
  
 Der für diese Aufgabe verwendete Code wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
### <a name="to-define-a-service-contract"></a>So definieren Sie einen Dienstvertrag  
  
1.  Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] als Administrator, indem Sie mit der rechten Maustaste des Programms in der **starten** Menü- und Auswählen von **als Administrator ausführen**.  
  
2.  Erstellen Sie einen WCF-Dienstbibliotheksprojekt, indem Sie auf die **Datei** Menü- und Auswählen von **neu**, **Projekt**. In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite des Dialogfelds **Visual C#-** für ein C#-Projekt oder **andere Sprachen** und dann **Visual Basic** für ein Visual Basic-Projekt. Wählen Sie unter der ausgewählten Sprache **WCF** und eine Liste der Projektvorlagen im mittleren Abschnitt des Dialogfelds angezeigt. Wählen Sie **WCF-Dienstbibliothek**, und geben `GettingStartedLib` in der **Namen** Textfeld und `GettingStarted` in der **Projektmappenname** Textfeld unten auf der das Dialogfeld ".  
  
3.  Visual Studio erstellt das Projekt, das 3 Dateien enthält: IService1.cs (oder IService1.vb),Service1.cs (oder Service1.vb) und App.config.  Die Datei IService1 enthält einen Standarddienstvertrag.  Die Datei Service1 enthält eine Standardimplementierung des Dienstvertrags. Die Datei App.config enthält die Konfiguration, die erforderlich ist, um den Standarddienst mit dem Visual Studio-WCF-Diensthost zu laden. Weitere Informationen zum WCF-Diensthost-Tool finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
4.  Öffnen Sie die Datei IService1.cs oder IService1.vb, und löschen Sie den Code in der Namespacedeklaration, wobei Sie die Namespacedeklaration beibehalten. Definieren Sie in der Namespacedeklaration eine neue Schnittstelle mit dem Namen `ICalculator`, wie im Code unten dargestellt.  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
            public interface ICalculator  
            {  
                [OperationContract]  
                double Add(double n1, double n2);  
                [OperationContract]  
                double Subtract(double n1, double n2);  
                [OperationContract]  
                double Multiply(double n1, double n2);  
                [OperationContract]  
                double Divide(double n1, double n2);  
            }  
    }  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
    ```  
  
     Dieser Vertrag definiert einen Onlinerechner. Beachten Sie, dass die `ICalculator`-Schnittstelle mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert ist. Dieses Attribut definiert einen Namespace, anhand dessen der Vertragsname eindeutig angegeben wird. Jeder Rechnervorgang wird mit dem <xref:System.ServiceModel.OperationContractAttribute>-Attribut markiert.  
  
    > [!NOTE]
    >  Wenn eine Schnittstelle, ein Member oder eine Klasse mithilfe von Attributen mit Anmerkungen versehen wird, können Sie auf die Angabe „Attribute“ im Namen des Attributs verzichten. Deshalb wird <xref:System.ServiceModel.ServiceContractAttribute> in C# zu `[ServiceContract]` oder in Visual Basic zu `<ServiceContract>`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Vorgehensweise: Implementieren eines WCF-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
