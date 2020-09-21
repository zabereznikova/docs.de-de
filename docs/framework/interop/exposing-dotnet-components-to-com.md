---
title: Verfügbarmachen von .NET-Komponenten im COM
description: Machen Sie .NET-Komponenten in COM verfügbar. Qualifizieren Sie .NET-Typen für die Interoperation. Wenden Sie Interop-Attribute an. Packen Sie eine Assembly für COM. Nutzen Sie einen verwalteten Typ aus COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: dc808f3e8d6bd89ba979d43e5b4ec9d787bd09b1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545258"
---
# <a name="exposing-net-components-to-com"></a>Verfügbarmachen von .NET-Komponenten im COM

Das Schreiben eines .NET-Typs und das Verwenden dieses Typs von nicht verwaltetem Code sind unterschiedliche Aktivitäten für Entwickler. Dieser Abschnitt beschreibt einige Tipps zum Schreiben von verwaltetem Code, der mit COM-Clients interagiert:

- [Qualifizieren von .NET-Typen für die Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).

     Alle verwalteten Typen, Methoden, Eigenschaften, Felder und Ereignisse, die für COM verfügbar gemacht werden sollen, müssen öffentlich sein. Typen müssen über einen öffentlichen parameterlosen Konstruktor verfügen, da dies der einzige Konstruktor ist, der über COM aufgerufen werden kann.

- [Anwenden von Interop-Attributen](../../standard/native-interop/apply-interop-attributes.md).

     Benutzerdefinierte Attribute in verwaltetem Code können die Interoperabilität einer Komponente verbessern.

- [Packen einer Assembly für COM](packaging-an-assembly-for-com.md).

     COM-Entwickler fordern möglicherweise, dass Sie die Schritte für Verweise und die Bereitstellung Ihrer Assemblys zusammenfassen.

 Darüber hinaus werden in diesem Abschnitt die Aufgaben im Zusammenhang mit der Nutzung eines verwalteten Typs von einem COM-Client beschrieben.

## <a name="to-consume-a-managed-type-from-com"></a>Nutzen eines verwalteten Typs von COM

1. [Registrieren von Assemblys bei COM](registering-assemblies-with-com.md).

     Typen in einer Assembly (und Typbibliotheken) müssen zur Entwurfszeit registriert werden. Wenn ein Installer die Assembly nicht registriert, weisen Sie die COM-Entwickler zur Nutzung von Regasm.exe an.

2. [Verweisen auf .NET-Typen in COM](how-to-reference-net-types-from-com.md).

     COM-Entwickler können auf Typen in einer Assembly verweisen, indem sie dieselben Tools und Techniken nutzen, die sie heute bereits verwenden.

3. [Aufrufen eines .NET-Objekts](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).

     COM-Entwickler können Methoden so für das .NET-Objekt aufrufen, wie sie Methoden für alle nicht verwalteten Typen aufrufen. Z.B. aktiviert die COM-API **CoCreateInstance** .NET-Objekte.

4. [Bereitstellen einer Anwendung für COM-Zugriff](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).

     Eine Assembly mit starkem Namen kann im globalen Assemblycache installiert werden und erfordert eine Signatur des Herausgebers. Assemblys, die keinen starken Namen haben, müssen im Anwendungsverzeichnis des Clients installiert werden.

## <a name="see-also"></a>Siehe auch

- [Interoperabilität mit nicht verwaltetem Code](index.md)
- [COM-Interopbeispiel: COM-Client und .NET-Server](com-interop-sample-com-client-and-net-server.md)
