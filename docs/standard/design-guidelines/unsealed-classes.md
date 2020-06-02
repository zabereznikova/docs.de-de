---
title: Unversiegelte Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8e332a6382cf644c82d5e26cf5234cea08dcc693
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289550"
---
# <a name="unsealed-classes"></a>Unversiegelte Klassen
Versiegelte Klassen können nicht von geerbt werden und verhindern die Erweiterbarkeit. Im Gegensatz dazu werden Klassen, die von geerbt werden können, als nicht versiegelte Klassen bezeichnet.

 ✔️ sollten Sie in Erwägung gezogen werden, nicht versiegelte Klassen ohne hinzugefügte virtuelle oder geschützte Member als hervorragend zu verwenden, um eine kostengünstige Erweiterbarkeit für ein Framework zu gewährleisten.

 Entwickler möchten häufig von nicht versiegelten Klassen erben, um bequeme Member wie benutzerdefinierte Konstruktoren, neue Methoden oder Methoden Überladungen hinzuzufügen. Beispielsweise `System.Messaging.MessageQueue` ist nicht versiegelt und ermöglicht Benutzern das Erstellen benutzerdefinierter Warteschlangen, die standardmäßig einen bestimmten Warteschlangen Pfad haben, oder das Hinzufügen von benutzerdefinierten Methoden, die die API für bestimmte Szenarien vereinfachen.

 Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt. Dies ist auch der empfohlene Standard für die meisten Klassen in Frameworks. Die Erweiterbarkeit, die von nicht versiegelten Typen geboten wird, wird von frameworkbenutzern erheblich geschätzt und ist aufgrund relativ niedriger Testkosten, die mit nicht versiegelten Typen verbunden sind, sehr kostengünstig.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwerfen für Erweiterbarkeit](designing-for-extensibility.md)
- [Versiegeln](sealing.md)
