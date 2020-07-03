---
title: 'Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation'
description: Hier erfahren Sie, wie Sie eine globale Proxyinstanz erstellen, damit WebRequest einen Proxy für die Kommunikation mit dem Internet im .NET Framework verwenden kann.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502534"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation

In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren. Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.

## <a name="example"></a>Beispiel

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Eine [`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) in C# für den Namespace **System.Net**
- Eine [`Imports`-Anweisung](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic für den Namespace **System.Net**

## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungsprotokollen](using-application-protocols.md)
- [Zugreifen auf das Internet über einen Proxy](accessing-the-internet-through-a-proxy.md)
