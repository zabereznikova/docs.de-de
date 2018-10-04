---
title: 'Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 9f7f696b1f5be2e96c50938f4627271d891deb32
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582199"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags
Dies ist der erste von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).

 Wenn Sie einen WCF-Dienst zu erstellen, ist die erste Aufgabe, um einen Dienstvertrag zu definieren. Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt. Ein Vorgang ähnelt einer Webdienstmethode. Verträge werden durch Definieren einer C++-, einer C#- oder einer Visual Basic (VB)-Schnittstelle erstellt. Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang. Auf jede Schnittstelle muss das <xref:System.ServiceModel.ServiceContractAttribute> angewendet werden, und auf jeden Vorgang muss das <xref:System.ServiceModel.OperationContractAttribute> angewendet werden. Wenn eine Methode in einer Schnittstelle, die über das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut verfügt, nicht das <xref:System.ServiceModel.OperationContractAttribute>-Attribut aufweist, wird diese Methode vom Dienst nicht verfügbar gemacht.

 Der für diese Aufgabe verwendete Code wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.

## <a name="define-a-service-contract"></a>Definieren eines Dienstvertrags

1. Öffnen Sie Visual Studio als Administrator, indem Sie mit der rechten Maustaste in des Programms in der **starten** Menü und auswählen **weitere** > **als Administrator ausführen**.

2. Erstellen eines WCF-Dienstbibliothek-Projekts.

   1. Wählen Sie im Menü **Datei** den Befehl **Neu** > **Projekt** aus.

   2. In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite **Visual C#-** oder **Visual Basic**, und wählen Sie dann die **WCF** Kategorie. Eine Liste der Projektvorlagen das Projekt wird im mittleren Abschnitt des Dialogfelds angezeigt. Wählen Sie **WCF-Dienstbibliothek**.

   3. Geben Sie `GettingStartedLib` in die **Namen** Textfeld und `GettingStarted` in die **Projektmappenname** Textfeld am unteren Rand des Dialogfelds.

   > [!NOTE]
   > Wenn Sie nicht sehen die **WCF** Vorlagenkategorie Projekt müssen Sie möglicherweise installieren die **Windows Communication Foundation** Komponente von Visual Studio. In der **neues Projekt** Dialogfeld klicken Sie auf den Link **Visual Studio-Installer öffnen**. Wählen Sie die **Einzelkomponenten** Registerkarte und suchen Sie dann aus, und wählen Sie **Windows Communication Foundation** unter der **Entwicklungsaktivitäten** Kategorie. Wählen Sie **ändern** zu beginnen, die Komponente zu installieren.

   Visual Studio erstellt das Projekt, das 3 Dateien enthält: IService1.cs (oder "IService1.vb"), Service1.cs (oder Service1.vb) und "App.config". Die Datei IService1 enthält einen Standarddienstvertrag. Die Datei Service1 enthält eine Standardimplementierung des Dienstvertrags. Die Datei App.config enthält die Konfiguration, die erforderlich ist, um den Standarddienst mit dem Visual Studio-WCF-Diensthost zu laden. Weitere Informationen zum Tool WCF-Diensthost finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

3. Öffnen Sie die Datei IService1.cs oder IService1.vb, und löschen Sie den Code in der Namespacedeklaration, verlassen die Namespacedeklaration. Definieren Sie in der Namespacedeklaration eine neue Schnittstelle mit dem Namen `ICalculator`, wie im Code unten dargestellt.

    ```csharp
    using System;
    using System.ServiceModel;

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

    ```vb
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

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Gewusst wie: implementieren ein Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Vorgehensweise: Implementieren eines WCF-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)