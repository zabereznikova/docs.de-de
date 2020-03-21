---
title: 'Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184091"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: Definieren eines Windows Communication Foundation-Dienstvertrags

In diesem Tutorial wird die erste von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Wenn Sie einen WCF-Dienst erstellen, besteht Ihre erste Aufgabe darin, einen Servicevertrag zu definieren. Im Dienstvertrag ist angegeben, welche Vorgänge vom Dienst unterstützt werden. Ein Vorgang ähnelt einer Webdienstmethode. Sie erstellen Serviceverträge, indem Sie eine C- oder Visual Basic-Schnittstelle definieren. Eine Schnittstelle weist die folgenden Eigenschaften auf:

- Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.
- Für jede Schnittstelle müssen <xref:System.ServiceModel.ServiceContractAttribute> Sie das Attribut anwenden.
- Für jede Operation/Methode müssen <xref:System.ServiceModel.OperationContractAttribute> Sie das Attribut anwenden.

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Erstellen Sie ein **WCF-Dienstbibliotheksprojekt.**
> - Definieren Sie eine Servicevertragsschnittstelle.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Erstellen eines WCF-Dienstbibliotheksprojekts und Definieren einer Servicevertragsschnittstelle

1. Öffnen Sie Visual Studio als Administrator. Wählen Sie dazu das Visual Studio-Programm im **Startmenü** aus, und wählen Sie dann im Kontextmenü **Mehr** > **Ausführen als Administrator** aus.

2. Erstellen Sie ein **WCF-Dienstbibliotheksprojekt.**

   1. Klicken Sie im Menü **Datei** auf **Neu** > **Projekt**.

   2. Erweitern Sie im Dialogfeld **Neues Projekt** auf der linken Seite Visual **C oder** Visual **Basic**, und wählen Sie dann die **WCF-Kategorie** aus. Visual Studio zeigt eine Liste der Projektvorlagen im mittleren Bereich des Fensters an. Wählen Sie **WCF-Dienstbibliothek**aus.

      > [!NOTE]
      > Wenn die **WCF-Projektvorlagenkategorie** nicht angezeigt wird, müssen Sie möglicherweise die Windows Communication **Foundation-Komponente** von Visual Studio installieren. Wählen Sie im Dialogfeld **Neues Projekt** den Link Visual Studio **Installer öffnen** auf der linken Seite aus. Wählen Sie die Registerkarte **Einzelne Komponenten** aus, und suchen Sie dann Windows **Communication Foundation** unter der Kategorie **Entwicklungsaktivitäten.** Wählen Sie **Ändern** aus, um mit der Installation der Komponente zu beginnen.

   3. Geben Sie im unteren Bereich des Fensters *GettingStartedLib* für den **Namen** und *GettingStarted* für den **Projektmappennamen**ein.

   4. Wählen Sie **OK** aus.

      Visual Studio erstellt das Projekt mit drei Dateien: *IService1.cs* (oder *IService1.vb* für ein Visual Basic-Projekt), *Service1.cs* (oder *Service1.vb* für ein Visual Basic-Projekt) und *App.config*. Visual Studio definiert diese Dateien wie folgt:
      - Die *IService1-Datei* enthält die Standarddefinition des Servicevertrags.
      - Die *Service1-Datei* enthält die Standardimplementierung des Servicevertrags.
      - Die *Datei App.config* enthält die Konfigurationsinformationen, die zum Laden des Standarddienstes mit dem Visual Studio WCF-Diensthosttool erforderlich sind. Weitere Informationen zum WCF-Diensthosttool finden Sie unter [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Wenn Sie Visual Studio mit den Visual Basic-Entwicklerumgebungseinstellungen installiert haben, ist die Lösung möglicherweise ausgeblendet. Wenn dies der Fall ist, **wählen** Sie optionen aus dem Menü **Extras** und dann im Fenster **Optionen** die Option **Projekte und Lösungen** > **Allgemein** aus. Wählen Sie **Immer Lösung anzeigen**. Überprüfen Sie außerdem, ob **neue Projekte beim Erstellen** speichern ausgewählt ist.

3. Öffnen Sie im **Projektmappen-Explorer**die **Datei IService1.cs** oder **IService1.vb,** und ersetzen Sie ihren Code durch den folgenden Code:

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

     Dieser Vertrag definiert einen Onlinerechner. Beachten `ICalculator` Sie, dass <xref:System.ServiceModel.ServiceContractAttribute> die Schnittstelle `ServiceContract`mit dem Attribut (vereinfacht als ) gekennzeichnet ist. Dieses Attribut definiert einen Namespace, um den Vertragsnamen zu disambiguieren. Der Code markiert jeden <xref:System.ServiceModel.OperationContractAttribute> Rechnervorgang mit `OperationContract`dem Attribut (vereinfacht als ).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> - Erstellen Sie ein WCF-Dienstbibliotheksprojekt.
> - Definieren Sie eine Servicevertragsschnittstelle.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Servicevertrag implementieren.

> [!div class="nextstepaction"]
> [Tutorial: Implementieren eines WCF-Dienstvertrags](how-to-implement-a-wcf-contract.md)
