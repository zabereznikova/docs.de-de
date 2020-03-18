---
title: 'Exemplarische Vorgehensweise: Beibehalten eines Objekts unter Verwendung von C#'
ms.date: 04/26/2018
ms.openlocfilehash: 85c5d1b711180eda5734d5860d996242c6bc89d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167569"
---
# <a name="walkthrough-persisting-an-object-using-c"></a>Exemplarische Vorgehensweise: Beibehalten eines Objekts unter Verwendung von C\#

Sie können die Serialisierung verwenden, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.

In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches `Loan`-Objekt und behalten dessen Daten in einer Datei bei. Anschließend rufen Sie die Daten aus der Datei ab, wenn Sie das Objekt neu erstellen.

> [!IMPORTANT]
> Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, muss Sie über die `Create`-Berechtigung für den Ordner verfügen. Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung `Write`, was einer geringeren Berechtigung entspricht. Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte die `Read`-Berechtigung nur für eine einzelne Datei erteilt werden (anstatt „Create“-Berechtigungen für den gesamten Ordner zu gewähren). Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programmdateien“ zu schreiben.

> [!IMPORTANT]
> In diesem Beispiel werden Daten in einer Datei im Binärformat gespeichert. Diese Formate sollten nicht für sensible Daten wie Kennwörter oder Kreditkarteninformationen verwendet werden.

## <a name="prerequisites"></a>Voraussetzungen

- Installieren Sie zum Erstellen und Ausführen von Builds das [.NET Core SDK](https://dotnet.microsoft.com/download).

- Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.

> [!TIP]
> Benötigen Sie einen Code-Editor? Testen Sie [Visual Studio](https://visualstudio.com/downloads).

- Dieses Beispiel erfordert C# 7.3. Siehe [Auswählen der C#-Sprachversion](../../../language-reference/configure-language-version.md).

Sie können den Beispielcode online im [GitHub-Repository für .NET-Beispiele](https://github.com/dotnet/samples/tree/master/csharp/serialization) untersuchen.

## <a name="creating-the-loan-object"></a>Erstellen des Loan-Objekts

Der erste Schritt ist das Erstellen einer `Loan`-Klasse und einer Konsolenanwendung, die die Klasse verwendet:

1. Erstellen Sie eine neue Anwendung. Geben Sie `dotnet new console -o serialization` ein, um eine neue Konsolenanwendung in einem Unterverzeichnis mit dem Namen `serialization` zu erstellen.
1. Öffnen Sie die Anwendung in Ihrem Editor, und fügen Sie eine neue Klasse mit dem Namen `Loan.cs` hinzu.
1. Fügen Sie der `Loan`-Klasse den folgenden Code hinzu:

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

Sie müssen ebenfalls eine einfache Anwendung erstellen, die die `Loan`-Klasse verwendet.

## <a name="serialize-the-loan-object"></a>Serialisieren des Loan-Objekts

1. Öffnen Sie `Program.cs`. Fügen Sie den folgenden Code hinzu:

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

Fügen Sie für das `PropertyChanged`-Ereignis einen Ereignishandler und einige Zeilen hinzu, um das `Loan`-Objekt zu bearbeiten und die Änderungen anzuzeigen. Im folgenden Code können Sie die Änderungen sehen:

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

Zu diesem Zeitpunkt können Sie den Code ausführen und die aktuelle Ausgabe sehen:

```console
New customer value: Henry Clay
7.5
7.1
```

Wenn Sie diese Anwendung wiederholt ausführen, werden immer dieselben Werte geschrieben. Jedes Mal, wenn Sie das Programm ausführen, wird ein neues Loan-Objekt erstellt. In der Praxis ändern sich Zinssätze regelmäßig, aber nicht unbedingt jedes Mal wenn die Anwendung ausgeführt wird. Mithilfe von Serialisierungscode speichern Sie die aktuellsten Zinssätze zwischen den einzelnen Anwendungsinstanzen. Im nächsten Schritt werden Sie durch Hinzufügen von Serialisierung zur Loan-Klasse genau das tun.

## <a name="using-serialization-to-persist-the-object"></a>Verwenden von Serialisierung zum Beibehalten des Objekts

Sie müssen die Klasse zuerst mit dem Attribut `Serializable` markieren, um die Werte für die Loan-Klasse beizubehalten. Fügen Sie den folgenden Code oberhalb der Definition der Loan-Klasse hinzu.

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

Der Compiler wird vom Attribut <xref:System.SerializableAttribute> darüber informiert, dass der Inhalt der Klasse in einer Datei beibehalten werden kann. Da das `PropertyChanged`-Ereignis keinen Teil des Objektgraphen darstellt, der gespeichert werden sollte, sollte es nicht serialisiert werden. Bei einer Serialisierung würden alle Objekte serialisiert werden, die diesem Ereignis zugeordnet sind. Sie können das <xref:System.NonSerializedAttribute>-Attribut zu der Felddeklaration für den Ereignishandler `PropertyChanged` hinzufügen.

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

Ab C# 7.3 können Sie Attribute an das Unterstützungsfeld einer automatisch implementierten Eigenschaft unter Verwendung des Zielwerts `field` anfügen. Über den folgenden Code fügen Sie eine `TimeLastLoaded`-Eigenschaft hinzu und markieren diese als „nicht serialisierbar“:

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

Fügen Sie als nächstes den Serialisierungscode zur LoanApp-Anwendung hinzu. Um die Klasse zu serialisieren und in eine Datei zu schreiben, verwenden Sie die Namespaces <xref:System.IO> und <xref:System.Runtime.Serialization.Formatters.Binary>. Sie können wie im folgenden Codebeispiel dargestellt Verweise zu den notwendigen Namespaces hinzufügen, damit Sie die vollqualifizierten Namen nicht eingeben müssen:

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

Fügen Sie als nächstes Code hinzu, um das Objekt aus der Datei zu deserialisieren wenn das Objekt erstellt wird. Fügen Sie wie im folgenden Codebeispiel dargestellt eine Konstante zur Klasse für den Dateinamen der serialisierten Daten hinzu:

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

Fügen Sie dann im Anschluss an die Zeile, die das `TestLoan`-Objekt erstellt, den folgenden Code hinzu:

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

Sie müssen erst sicherstellen, ob die Datei vorhanden ist. Wenn sie vorhanden ist, erstellen Sie eine <xref:System.IO.Stream>-Klasse zum Lesen der Binärdatei und eine <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Klasse zum Übersetzen der Datei. Sie müssen ebenfalls vom Streamtyp in den Loan-Objekttyp konvertieren.

Als nächstes müssen Sie Code hinzufügen, um die Klasse in eine Datei zu serialisieren. Fügen Sie dem vorhandenen Code den folgenden Code in der `Main`-Methode hinzu:

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

Nun können Sie die Anwendung erneut erstellen und ausführen. Beachten Sie, dass die Zinssätze bei der ersten Ausführung bei 7,5 beginnen und dann in 7,1 umgewandelt werden. Schließen Sie die Anwendung, und führen Sie sie dann erneut aus. Die Anwendung druckt dann die Meldung aus, die sie aus der gespeicherten Datei gelesen hat. Der Zinssatz liegt dann sogar vor dem Code, der diese ändert, bei 7,1.

## <a name="see-also"></a>Weitere Informationen

- [Serialisierung (C#)](index.md)
- [C#-Programmierhandbuch](../..//index.md)
