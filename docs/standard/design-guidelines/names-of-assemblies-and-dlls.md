---
title: Namen von Assemblys und DLLs
description: Erfahren Sie mehr über Richtlinien für das Benennen von Assemblys und Dynamic Link Libraries (DLLs). Eine Assembly kann eine oder mehrere Dateien umfassen, Sie ordnet jedoch in der Regel eins-zu-eins einer DLL zu.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: 2d1484889eb7db537de970c31109f26a6d61ad8d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830050"
---
# <a name="names-of-assemblies-and-dlls"></a>Namen von Assemblys und DLLs
Eine Assembly ist die Bereitstellungs Einheit und Identität für verwaltete Code Programme. Assemblys können sich über eine oder mehrere Dateien erstrecken. in der Regel ordnet eine Assembly eins-zu-eins einer DLL zu. In diesem Abschnitt werden daher nur dll-Benennungs Konventionen beschrieben, die dann assemblybenennungs Konventionen zugeordnet werden können.

 ✔️ Wählen Sie Namen für die assemblydlls aus, die große Funktionsblöcke vorschlagen, wie z. b. System. Data.

 Assemblynamen und DLL-Namen müssen nicht den Namespace Namen entsprechen, aber es ist sinnvoll, beim Benennen von Assemblys den Namespace Namen zu befolgen. Eine gute Faustregel besteht darin, die dll basierend auf dem gemeinsamen Präfix der in der Assembly enthaltenen Namespaces zu benennen. Beispielsweise kann eine Assembly mit zwei Namespaces ( `MyCompany.MyTechnology.FirstFeature` und) `MyCompany.MyTechnology.SecondFeature` aufgerufen werden `MyCompany.MyTechnology.dll` .

 ✔️ in Erwägung gezogen, DLLs gemäß folgendem Muster zu benennen:

 `<Company>.<Component>.dll`

 , wobei `<Component>` eine oder mehrere durch Punkte getrennte Klauseln enthält. Beispiel:

 `Litware.Controls.dll`.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Benennungs Richtlinien](naming-guidelines.md)
