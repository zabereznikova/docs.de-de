---
title: "Exemplarische Vorgehensweise – zugreifen auf einen Webdienst mithilfe von Typanbietern (f#)"
description: "Erfahren Sie, wie mit der Web Services Description Language (WSDL) vom Typanbieter in f# 3.0 verfügbare WSDL-Dienst zuzugreifen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 06d955033d465cf58af05f483d21175f90d1777a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>Exemplarische Vorgehensweise: Zugreifen auf einen Webdienst mithilfe von Typanbietern

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](http://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In dieser exemplarischen Vorgehensweise wird erläutert, wie der in F# 3.0 verfügbare WSDL-Typanbieter (Web Services Description Language) verwendet wird, um auf einen WSDL-Dienst zuzugreifen. In anderen .NET-Sprachen generieren Sie Code, um über einen Aufruf von svcutil.exe auf den Webdienst zuzugreifen, oder Sie fügen einen Webverweis hinzu, beispielsweise in einem C#-Projekt, bei dem von Visual Studio ebenfalls svcutil.exe aufgerufen wird. In F# haben Sie zusätzlich die Option, den WSDL-Typanbieter zu verwenden, sodass in dem Moment, in dem Sie den Code zum Erstellen des WsdlService-Typs schreiben, die benötigten Typen generiert werden und zur Verfügung stehen. Für diesen Prozess muss der Dienst verfügbar sein, während Sie den Code schreiben.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben. Sie müssen alle Aufgaben ausführen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:


- Erstellen des Projekts
<br />

- Konfigurieren des Typanbieters
<br />

- Den Webdienst aufrufen und die Ergebnisse verarbeiten
<br />


## <a name="creating-the-project"></a>Erstellen des Projekts
In dem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise hinzu, um einen WSDL-Typanbieter zu verwenden.


#### <a name="to-create-and-set-up-an-f-project"></a>So erstellen und richten Sie ein F#-Projekt ein

1. Erstellen Sie ein neues F#-Konsolenanwendungsprojekt.
<br />

2. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für des Projekts **Verweis** Knoten, und wählen Sie dann **Verweis hinzufügen**.
<br />

3. In der **Assemblys** Bereich auswählen **Framework**, und wählen Sie dann in der Liste der verfügbaren Assemblys **System.Runtime.Serialization** und  **System.ServiceModel**.
<br />

4. In der **Assemblys** Bereich auswählen **Erweiterungen**.
<br />

5. Wählen Sie in der Liste der verfügbaren Assemblys, **FSharp.Data.TypeProviders**, und wählen Sie dann die **OK** Schaltfläche, um Verweise auf diese Assemblys hinzuzufügen.
<br />

## <a name="configuring-the-type-provider"></a>Konfigurieren des Typanbieters
In diesem Schritt verwenden Sie den WSDL-Typanbieter, um Typen für den TerraServer-Webdienst zu generieren.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>So konfigurieren Sie den Typanbieter und generieren Typen

1. Fügen Sie die folgende Codezeile hinzu, um den Typanbieternamespace zu öffnen.
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. Fügen Sie die folgende Codezeile hinzu, um den Typanbieter mit einem Webdienst aufzurufen. In diesem Beispiel wird der TerraServer-Webdienst verwendet.
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "http://terraserver-usa.com/TerraService2.asmx?WSDL" http://msrmaps.com/TerraService2.asmx?WSDL">
```

  Wenn der Dienst-URI falsch geschrieben oder der Dienst deaktiviert bzw. nicht erreichbar ist, wird unter dieser Codezeile eine rote Wellenlinie angezeigt. Wenn Sie auf den Code zeigen, beschreibt eine Fehlermeldung das Problem. Sie finden die gleiche Informationen in der **Fehlerliste** Fenster oder in der **Fenster "Ausgabe"** Nachdem Sie erstellt haben.
<br />  Es gibt zwei Möglichkeiten, Konfigurationseinstellungen für eine WSDL-Verbindung anzugeben: Entweder durch Verwendung der Datei app.config des Projekts oder durch Verwendung der statischen Typparameter in der Typanbieterdeklaration. Sie können svcutil.exe verwenden, um entsprechende Konfigurationsdateielemente zu generieren. Weitere Informationen zur Verwendung von svcutil.exe zum Generieren von Konfigurationsinformationen für einen Webdienst finden Sie unter [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx). Eine vollständige Beschreibung der statischen Typparameter für den WSDL-Typanbieter, finden Sie unter [WsdlService-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>Den Webdienst aufrufen und die Ergebnisse verarbeiten
Jeder Webdienst verfügt über eine eigene Gruppe von Typen, die als Parameter für die Methodenaufrufe verwendet werden. In diesem Schritt bereiten Sie diese Parameter vor, rufen eine Webmethode auf und verarbeiten die von der Methode zurückgegebenen Informationen.


#### <a name="to-call-the-web-service-and-process-the-results"></a>So rufen Sie den Webdienst auf und verarbeiten die Ergebnisse

1. Da es vorkommen kann, dass beim Webdienst ein Timeout auftritt oder der Dienst ausfällt, sollte der Aufruf des Webdiensts in einen Ausnahmebehandlungsblock eingeschlossen werden. Fügen Sie den folgenden Code ein, mit dem versucht wird, Daten von einem Webdienst abzurufen.
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

Beachten Sie, dass die Datentypen zu erstellen, die für den Webdienst, z. B. erforderlich sind **Stelle** und **Speicherort**, wie geschachtelte Typen unter dem WsdlService-Typs **TerraService**.
<br />


## <a name="see-also"></a>Siehe auch
[WsdlService-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[Typanbieter](index.md)
