---
title: Gründe für das Implementieren des ereignisbasierten asynchronen Musters
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
ms.openlocfilehash: 5fca32953af91184fe99d8ef6afe5a2374f325d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67663718"
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Gründe für das Implementieren des ereignisbasierten asynchronen Musters

Mit dem ereignisbasierten asynchronen Muster kann das asynchrone Verhalten einer Klasse verfügbar gemacht werden. Mit der Einführung dieses Musters definiert .NET Framework zwei Muster, um asynchrones Verhalten verfügbar zu machen: das asynchrone Muster basierend auf der <xref:System.IAsyncResult?displayProperty=nameWithType>-Schnittstelle und das ereignisbasierte Muster. In diesem Thema wird beschrieben, in welchen Fällen die Muster implementiert werden sollten.

Weitere Informationen zur asynchronen Programmierung mit der <xref:System.IAsyncResult>-Benutzeroberfläche finden Sie unter [Asynchrones Programmiermodell (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).

## <a name="general-principles"></a>Allgemeine Prinzipien

Allgemein sollten Sie asynchrone Features, die das ereignisbasierte asynchrone Muster verwenden, nach Möglichkeit verfügbar machen. Es gibt jedoch einige Anforderungen, die das ereignisbasierte Muster nicht erfüllen kann. In diesen Fällen müssen Sie neben dem ereignisbasierten Muster möglicherweise auch das <xref:System.IAsyncResult>-Muster implementieren.

> [!NOTE]
> Das <xref:System.IAsyncResult>-Muster wird in den meisten Fällen zusammen mit dem ereignisbasierten Muster implementiert.

## <a name="guidelines"></a>Richtlinien

In der folgenden Liste werden die Richtlinien beschrieben, in welchen Fällen das ereignisbasierte asynchrone Muster implementiert werden sollte:

- Verwenden Sie das ereignisbasierte Muster als Standard-API, um asynchrones Verhalten für Ihre Klasse verfügbar zu machen.

- Machen Sie das <xref:System.IAsyncResult>-Muster nicht verfügbar, wenn Ihre Klasse in erster Linie in einer Clientanwendung wie Windows Forms eingesetzt wird.

- Machen Sie das <xref:System.IAsyncResult>-Muster nur verfügbar, wenn dies zur Erfüllung Ihrer Anforderungen notwendig ist. Das <xref:System.IAsyncResult>-Muster muss beispielsweise verfügbar gemacht werden, um Kompatibilität mit einer vorhandenen API herzustellen.

- Machen Sie das <xref:System.IAsyncResult>-Muster nur in Verbindung mit dem ereignisbasierten Muster verfügbar.

- Wenn Sie das <xref:System.IAsyncResult>-Muster verfügbar machen, verwenden Sie hierfür eine erweiterte Option. Wenn Sie beispielsweise ein Proxyobjekt generieren, generieren Sie standardmäßig das ereignisbasierte Muster mit einer Option zum Generieren des <xref:System.IAsyncResult>-Musters.

- Ziehen Sie als Grundlage für die Implementierung Ihres ereignisbasierten Musters die Implementierung Ihres <xref:System.IAsyncResult>-Musters heran.

- Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>-Muster nicht für die gleiche Klasse verfügbar. Machen Sie das ereignisbasierte Muster für übergeordnete Klassen und das <xref:System.IAsyncResult>-Muster Klassen für untergeordnete Klassen verfügbar. Vergleichen Sie z.B. das ereignisbasierte Muster für die <xref:System.Net.WebClient>-Komponente mit dem <xref:System.IAsyncResult>-Muster für die <xref:System.Web.HttpRequest>-Klasse.

  - Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>-Muster für die gleiche Klasse verfügbar, wenn dies zur Bereitstellung von Kompatibilität erforderlich ist. Wenn Sie z.B. bereits eine API freigegeben haben, die das <xref:System.IAsyncResult>-Muster verwendet, müssten Sie das <xref:System.IAsyncResult>-Muster zum Bereitstellen von Abwärtskompatibilität beibehalten.

  - Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>-Muster für die gleiche Klasse verfügbar, wenn die resultierende Objektmodellkomplexität den Vorteil einer Trennung der Implementierungen überwiegt. Es ist besser, beide Muster für eine einzelne Klasse verfügbar zu machen, als auf die Bereitstellung des ereignisbasierten Musters zu verzichten.

  - Wenn Sie sowohl das ereignisbasierte Muster als auch das <xref:System.IAsyncResult>-Muster für eine einzelne Klasse verfügbar machen müssen, legen Sie <xref:System.ComponentModel.EditorBrowsableAttribute> auf <xref:System.ComponentModel.EditorBrowsableState.Advanced> fest, um die Implementierung des <xref:System.IAsyncResult>-Musters als erweitertes Feature zu kennzeichnen. Dies ist ein Hinweis für Entwurfsumgebungen wie Visual Studio IntelliSense, nicht die <xref:System.IAsyncResult>-Eigenschaften und -Methoden anzuzeigen. Diese Eigenschaften und Methoden sind weiterhin im vollen Umfang nutzbar, aber Entwickler, die mit IntelliSense arbeiten, haben einen umfassenderen Überblick über die API.

## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Kriterien für das Verfügbarmachen des IAsyncResult-Musters zusätzlich zum ereignisbasierten Muster

Das ereignisbasierte asynchrone Muster bietet zwar zahlreiche Vorteile im Zusammenhang mit den zuvor erläuterten Szenarien, bringt jedoch auch einige Nachteile mit sich, die Sie berücksichtigen sollten, wenn Leistung an oberster Stelle für Sie steht.

Es gibt drei Szenarien, die weder das ereignisbasierte Muster noch das <xref:System.IAsyncResult>-Muster bewältigen:

- Blockieren des Wartevorgangs bei einem <xref:System.IAsyncResult>-Objekt

- Blockieren des Wartevorgang bei vielen <xref:System.IAsyncResult>-Objekten

- Abrufen der Beendigung bezüglich <xref:System.IAsyncResult>

Diese Szenarien können mithilfe des ereignisbasierten Musters bewältigt werden, was jedoch umständlicher ist als die Verwendung des <xref:System.IAsyncResult>-Musters.

Entwickler verwenden häufig das <xref:System.IAsyncResult>-Muster für Dienste, die üblicherweise eine sehr hohe Leistung erfordern. Der Abruf des Beendigungsszenarios ist beispielsweise ein leistungsintensives Serververfahren.

Darüber hinaus ist das ereignisbasierte Muster weniger effizient als das <xref:System.IAsyncResult>-Muster, da mehrere Objekte, insbesondere <xref:System.EventArgs>, erstellt werden und es threadübergreifend synchronisiert wird.

Die folgende Liste enthält einige Empfehlungen, die Sie bei Verwendung des <xref:System.IAsyncResult>-Musters berücksichtigen sollten:

- Machen Sie das <xref:System.IAsyncResult>-Muster nur verfügbar, wenn Sie insbesondere Unterstützung für <xref:System.Threading.WaitHandle>- oder <xref:System.IAsyncResult>-Objekte benötigen.

- Machen Sie das <xref:System.IAsyncResult>-Muster nur verfügbar, wenn Sie eine API basierend auf diesem <xref:System.IAsyncResult>-Muster besitzen.

- Wenn Sie über eine API basierend auf dem <xref:System.IAsyncResult>-Muster verfügen, sollten Sie das ereignisbasierte Muster zudem im nächsten Release verfügbar machen.

- Machen Sie das <xref:System.IAsyncResult>-Muster nur verfügbar, wenn Sie über hohe Leistungsanforderungen verfügen, die gemäß Ihrer Feststellung nicht mit dem ereignisbasierten Muster, jedoch mit dem <xref:System.IAsyncResult>-Muster erfüllt werden können.

## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)
- [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
