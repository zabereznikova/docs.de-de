---
title: 'Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228392"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags

In diesem Tutorial wird die erste von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung beschrieben. Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Bei der Erstellung eines WCF-Diensts ist die erste Aufgabe, um einen Dienstvertrag zu definieren. Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt. Ein Vorgang ähnelt einer Webdienstmethode. Sie erstellen Dienstverträge definieren eine Visualisierung C# oder Visual Basic (VB)-Schnittstelle. Eine Schnittstelle weist folgende Merkmale auf:

- Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang. 
- Sie müssen für jede Schnittstelle, Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> Attribut.
- Sie müssen für jede vorgangsmethode/Anwenden der <xref:System.ServiceModel.OperationContractAttribute> Attribut. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen Sie eine **WCF-Dienstbibliothek** Projekt.
> - Definieren Sie eine dienstvertragsschnittstelle.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Erstellen Sie ein Projekt für die WCF-Dienstbibliothek und definieren eine dienstvertragsschnittstelle

1. Öffnen Sie Visual Studio als Administrator. Zu diesem Zweck wählen Sie das Visual Studio-Programm in der **starten** Menü, und wählen Sie dann **weitere** > **als Administrator ausführen** aus dem Kontextmenü.

2. Erstellen Sie eine **WCF-Dienstbibliothek** Projekt.

   1. Wählen Sie im Menü **Datei** den Befehl **Neu** > **Projekt** aus.

   2. In der **neues Projekt** erweitern Sie im Dialogfeld auf der linken Seite **Visual C#-** oder **Visual Basic**, und wählen Sie dann die **WCF** Kategorie. Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Abschnitt des Fensters. Wählen Sie **WCF-Dienstbibliothek**.

      > [!NOTE]
      > Wenn Sie nicht sehen die **WCF** Vorlagenkategorie Projekt müssen Sie möglicherweise installieren die **Windows Communication Foundation** Komponente von Visual Studio. In der **neues Projekt** wählen Sie im Dialogfeld die **Visual Studio-Installer öffnen** Link auf der linken Seite. Wählen Sie die **Einzelkomponenten** Registerkarte und suchen Sie dann aus, und wählen Sie **Windows Communication Foundation** unter der **Entwicklungsaktivitäten** Kategorie. Wählen Sie **ändern** zu beginnen, die Komponente zu installieren.

   3. Geben Sie im unteren Bereich des Fensters ein, *GettingStartedLib* für die **Namen** und *GettingStarted* für die **Projektmappenname**. 

   4. Klicken Sie auf **OK**.

      Visual Studio erstellt das Projekt, das drei Dateien enthält: *IService1.cs* (oder *"IService1.vb"* für Visual Basic-Projekt), *Service1.cs* (oder *Service1.vb* für Visual Basic-Projekt), und  *Datei "App.config"*. Visual Studio werden diese Dateien wie folgt definiert: 
      - Die *IService1* -Datei enthält die Default-Definition des Dienstvertrags. 
      - Die *"Service1"* -Datei enthält die standardmäßige Implementierung des Dienstvertrags. 
      - Die *"App.config"* -Datei enthält die Konfigurationsinformationen, die erforderlich sind, um den Standarddienst mit dem Visual Studio-WCF-Diensthost-Tool zu laden. Weitere Informationen zum Tool WCF-Diensthost finden Sie unter [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Wenn Sie Visual Studio mit Visual Basic-entwicklereinstellungen Umgebung installiert haben, kann die Lösung ausgeblendet werden. Wenn dies der Fall ist, wählen Sie **Optionen** aus der **Tools** Menü Wählen Sie dann **Projekte und Projektmappen** > **allgemeine** in die **Optionen** Fenster. Wählen Sie **Projektmappe immer anzeigen**. Darüber hinaus überprüfen Sie, ob **neue Projekte beim Erstellen speichern** ausgewählt ist.

3. Von **Projektmappen-Explorer**öffnen die **IService1.cs** oder **"IService1.vb"** Datei aus, und Ersetzen Sie den Code durch den folgenden Code:

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

     Dieser Vertrag definiert einen Onlinerechner. Beachten Sie, dass die `ICalculator` Schnittstelle ist mit markiert die <xref:System.ServiceModel.ServiceContractAttribute> Attribut (als vereinfachte `ServiceContract`). Dieses Attribut definiert einen Namespace aus, um der Vertragsname eindeutig zu machen. Der Code markiert jeder rechnervorgang wird mit der <xref:System.ServiceModel.OperationContractAttribute> Attribut (als vereinfachte `OperationContract`).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen eines WCF-Dienstbibliothek-Projekts.
> - Definieren Sie eine dienstvertragsschnittstelle.

Fahren Sie fort mit dem nächsten Tutorial erfahren, wie die WCF-Dienstvertrag implementiert.

> [!div class="nextstepaction"]
> [Tutorial: Implementieren eines WCF-Dienstvertrags](how-to-implement-a-wcf-contract.md)
