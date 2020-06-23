---
title: 'Tutorial: Definieren eines Windows Communication Foundation Service-Vertrags'
description: Erfahren Sie, wie Sie einen Dienstvertrag als Teil einer Reihe von Artikeln definieren, die Ihnen beim Einstieg in die Erstellung einer WCF-Anwendung helfen.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246310"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: Definieren eines Windows Communication Foundation Service-Vertrags

In diesem Tutorial werden die ersten von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).

Wenn Sie einen WCF-Dienst erstellen, besteht die erste Aufgabe darin, einen Dienstvertrag zu definieren. Im Dienstvertrag ist angegeben, welche Vorgänge vom Dienst unterstützt werden. Ein Vorgang ähnelt einer Webdienstmethode. Sie erstellen Dienstverträge, indem Sie eine c#-oder Visual Basic-Schnittstelle definieren. Eine Schnittstelle verfügt über die folgenden Eigenschaften:

- Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.
- Für jede Schnittstelle müssen Sie das- <xref:System.ServiceModel.ServiceContractAttribute> Attribut anwenden.
- Für jeden Vorgang/jede Methode müssen Sie das- <xref:System.ServiceModel.OperationContractAttribute> Attribut anwenden.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen Sie ein **WCF-Dienst Bibliotheks** Projekt.
> - Definieren Sie eine Dienstvertragschnittstelle.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Erstellen eines WCF-Dienst Bibliotheks Projekts und Definieren einer Dienstvertrags Schnittstelle

1. Öffnen Sie Visual Studio als Administrator. Wählen Sie hierzu im **Startmenü** das Visual Studio-Programm aus, und wählen Sie dann im Kontextmenü die Option **Weitere**  >  **als Administrator ausführen** aus.

2. Erstellen Sie ein **WCF-Dienst Bibliotheks** Projekt.

   1. Klicken Sie im Menü **Datei** auf **Neu** > **Projekt**.

   2. Erweitern Sie im Dialogfeld **Neues Projekt** auf der linken Seite **Visual c#** oder **Visual Basic**, und wählen Sie dann die Kategorie **WCF** aus. Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Abschnitt des Fensters an. Wählen Sie **WCF-Dienst Bibliothek**aus.

      > [!NOTE]
      > Wenn die Kategorie **WCF** -Projektvorlage nicht angezeigt wird, müssen Sie möglicherweise die **Windows Communication Foundation** Komponente von Visual Studio installieren. Wählen Sie im Dialogfeld **Neues Projekt** den Link **Visual Studio-Installer öffnen** auf der linken Seite aus. Wählen Sie die Registerkarte **einzelne Komponenten** aus, suchen Sie nach **Windows Communication Foundation** unter der Kategorie **Entwicklungsaktivitäten** , und wählen Sie ihn aus. Wählen Sie **ändern** aus, um die Installation der Komponente zu starten

   3. Geben Sie im unteren Abschnitt des Fensters *gettingstartedlib* als **Name** und *GettingStarted* als Projektmappenname **Solution name**ein.

   4. Klicken Sie auf **OK**.

      Visual Studio erstellt das Projekt, das über drei Dateien verfügt *: IService1.cs* ( *oder IService1. vb* für ein Visual Basic Projekt), *Service1.cs* (oder *Service1. vb* für ein Visual Basic Projekt) und *App.config*. Diese Dateien werden von Visual Studio wie folgt definiert:
      - Die *IService1* -Datei enthält die Standard Definition des Dienstvertrags.
      - Die *Service1* -Datei enthält die Standard Implementierung des Dienstvertrags.
      - Die *App.config* -Datei enthält die Konfigurationsinformationen, die zum Laden des Standard Diensts mit dem Visual Studio WCF-Dienst Host Tool erforderlich sind. Weitere Informationen zum WCF-Dienst Host Tool finden Sie unter [WCF-Dienst Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Wenn Sie Visual Studio mit Visual Basic Einstellungen für die Entwicklerumgebung installiert haben, ist die Projekt Mappe möglicherweise ausgeblendet. Wenn dies der Fall ist, wählen Sie im Menü **Extras die** **Option Optionen** aus, und wählen Sie dann im Fenster Optionen die Option **Projekte und Projekt**Mappen  >  **Allgemein** aus. **Options** Wählen Sie Projekt Mappe **immer anzeigen**aus. Vergewissern Sie sich außerdem, dass **neue Projekte beim Erstellen speichern** ausgewählt ist.

3. Öffnen Sie die Datei **IService1.cs** oder **IService1. vb** von **Projektmappen-Explorer**, und ersetzen Sie den Code durch den folgenden Code:

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

     Dieser Vertrag definiert einen Onlinerechner. Beachten Sie, dass die- `ICalculator` Schnittstelle mit dem-Attribut markiert ist <xref:System.ServiceModel.ServiceContractAttribute> (vereinfacht als `ServiceContract` ). Dieses Attribut definiert einen Namespace, um den Vertrags Namen eindeutig zu machen. Der Code markiert jeden Rechner Vorgang mit dem- <xref:System.ServiceModel.OperationContractAttribute> Attribut (vereinfacht als `OperationContract` ).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> - Erstellen Sie ein WCF-Dienst Bibliotheksprojekt.
> - Definieren Sie eine Dienstvertragschnittstelle.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienstvertrag implementieren.

> [!div class="nextstepaction"]
> [Tutorial: Implementieren eines WCF-Dienstvertrags](how-to-implement-a-wcf-contract.md)
