---
title: Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 01184969b7bfcc0f68351db7c8daeebe79be583c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392322"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)

Dies ist die zweite Aufgabe des Schnellstarts WCF Data Services. In dieser Aufgabe starten den WCF Data Services in Visual Studio und deaktivieren optional feedlesen im Webbrowser. Sie klicken Sie dann rufen den Dienst als auch Zugriff auf datendienstressourcen von HTTP GET-Anforderungen über einen Webbrowser an die verfügbar gemachten Ressourcen senden.

> [!NOTE]
> Standardmäßig weist Visual Studio dem `localhost`-URI auf dem Computer automatisch eine Portnummer zu. Für diese Aufgabe wird in den URI-Beispielen die Portnummer `12345` verwendet. Weitere Informationen zum Festlegen eine bestimmten Portnummer in Visual Studio-Projekts finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>So fordern Sie das Standarddienstdokument mithilfe von Internet Explorer an

1.  In Internet Explorer aus der **Tools** , wählen Sie im Menü **Internetoptionen**, klicken Sie auf die **Content** auf **Einstellungen**, und Deaktivieren von  **Die Feedleseanzeige einschalten**.

     Dadurch wird sichergestellt, dass das Lesen von Feeds deaktiviert ist. Wenn Sie diese Funktionalität nicht deaktivieren, behandelt der Webbrowser das zurückgegebene AtomPub-codierte Dokument als XML-Feed, statt die unformatierten XML-Daten anzuzeigen.

    > [!NOTE]
    > Wenn der Browser den Feed nicht als unformatierte XML-Daten anzeigen kann, sollten es dennoch möglich sein, den Feed als Quellcode der Seite anzuzeigen.

2.  Drücken Sie in Visual Studio die **F5** Schlüssel zum Starten des Debuggings der Anwendungs.

3.  Öffnen Sie auf dem lokalen Computer einen Webbrowser. Geben Sie in der Adressleiste den folgenden URI ein:

    ```
    http://localhost:12345/northwind.svc
    ```

     Dadurch wird das Standarddienstdokument zurückgegeben, das eine Liste von Entitätenmengen enthält, die von diesem Datendienst verfügbar gemacht werden.

## <a name="to-access-entity-set-resources-from-a-web-browser"></a>So greifen Sie auf Entitätenmengenressourcen in einem Webbrowser zu

1.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     Dadurch wird ein Satz aller Kunden in der Northwind-Beispieldatenbank zurückgegeben.

2.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     Dadurch wird eine Entitätsinstanz für einen bestimmten Kunden, `ALFKI`, zurückgegeben.

3.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     Dadurch wird die Beziehung zwischen Kunden und Bestellungen durchlaufen, um einen Satz aller Bestellungen für den Kunden `ALFKI` zurückzugeben.

4.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     Dadurch werden Bestellungen gefiltert, die zum Kunden `ALFKI` gehören, sodass auf der Grundlage des angegebenen `OrderID`-Werts nur eine bestimmte Bestellung zurückgegeben wird.

## <a name="next-steps"></a>Nächste Schritte

Sie haben erfolgreich die WCF Data Services über einen Webbrowser, mit der Browser HTTP GET-Anforderungen ausgegeben an angegebene Ressourcen zugegriffen hat. Mithilfe eines Webbrowsers können Sie leicht mit der Adressierungssyntax von Anforderungen experimentieren und die Ergebnisse anzeigen. Auf einen Produktionsdatendienst wird jedoch im Allgemeinen nicht mit dieser Methode zugegriffen. Normalerweise interagieren Anwendungen mit dem Datendienst über Anwendungscode oder Skriptsprachen. Als Nächstes erstellen Sie eine Clientanwendung, die Clientbibliotheken verwendet, um auf Datendienstressourcen zuzugreifen, als ob sie Common Language Runtime (CLR)-Objekte wären:

> [!div class="nextstepaction"]
> [Erstellen der .NET Framework-Clientanwendung](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Siehe auch

- [Zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
