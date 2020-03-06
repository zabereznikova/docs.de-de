---
title: C#-Schnittstellen – Überblick über C#
description: Schnittstellen definieren von Typen in C# implementierte Verträge.
ms.date: 02/27/2020
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 62d94462fa481379cf70d63a598deb7f36be204f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159129"
---
# <a name="interfaces"></a>Schnittstellen

Eine ***Schnittstelle*** definiert einen Vertrag, der von Klassen und Strukturen implementiert werden kann. Eine Schnittstelle kann Methoden, Eigenschaften, Ereignisse und Indexer enthalten. Eine Schnittstelle stellt keine Implementierungen der von ihr definierten Member bereit. Sie gibt lediglich die Member an, die von Klassen oder Strukturen bereitgestellt werden müssen, die die Schnittstelle implementieren.

Schnittstellen können ***Mehrfachvererbung*** einsetzen. Im folgenden Beispiel erbt die Schnittstelle `IComboBox` sowohl von `ITextBox` als auch `IListBox`.

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

Klassen und Strukturen können mehrere Schnittstellen implementieren. Im folgenden Beispiel implementiert die Klasse `EditBox` sowohl `IControl` als auch `IDataBound`.

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

Wenn eine Klasse oder Struktur eine bestimmte Schnittstelle implementiert, können Instanzen dieser Klasse oder Struktur implizit in diesen Schnittstellentyp konvertiert werden. Beispiel:

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

In Fällen, in denen nicht bekannt ist, dass eine Instanz eine bestimmte Schnittstelle implementiert, können dynamische Typumwandlungen verwendet werden. Beispielsweise verwenden die folgenden Anweisungen dynamische Typumwandlungen zum Abrufen der `IControl`- und `IDataBound`-Schnittstellenimplementierungen eines Objekts. Da der eigentliche Laufzeittyp des Objekts `EditBox` ist, sind die Umwandlungen erfolgreich.

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

In der vorherigen `EditBox`-Klasse werden die `Paint`-Methode aus der `IControl`-Schnittstelle und die `Bind`-Methode aus der `IDataBound`-Schnittstelle mithilfe öffentlicher Member implementiert. C# unterstützt außerdem explizite ***Implementierungen eines Schnittstellenmembers***, sodass die Klasse oder Struktur vermeiden können, die Member öffentlich zu machen. Eine explizite Implementierung eines Schnittstellenmembers wird mit dem vollqualifizierten Namen des Schnittstellenmembers geschrieben. Die `EditBox`-Klasse könnte z.B. die `IControl.Paint`- und `IDataBound.Bind`-Methode wie folgt über explizite Implementierungen eines Schnittstellenmembers implementieren.

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

Der Zugriff auf explizite Schnittstellenmember kann nur über den Schnittstellentyp erfolgen. Die von der vorherigen EditBox-Klasse bereitgestellte Implementierung von `IControl.Paint` kann z.B. nur aufgerufen werden, indem zuerst der `EditBox`-Verweis in den `IControl`-Schnittstellentyp konvertiert wird.

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
>[Zurück](arrays.md)
>[Weiter](delegates.md)
