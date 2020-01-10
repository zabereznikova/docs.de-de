---
title: Namen von Assemblys und DLLs
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709256"
---
# <a name="names-of-assemblies-and-dlls"></a>Namen von Assemblys und DLLs
Eine Assembly ist die Bereitstellungs Einheit und Identität für verwaltete Code Programme. Assemblys können sich über eine oder mehrere Dateien erstrecken. in der Regel ordnet eine Assembly eins-zu-eins einer DLL zu. In diesem Abschnitt werden daher nur dll-Benennungs Konventionen beschrieben, die dann assemblybenennungs Konventionen zugeordnet werden können.  
  
 **✓ DO** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.  
  
 Assemblynamen und DLL-Namen müssen nicht den Namespace Namen entsprechen, aber es ist sinnvoll, beim Benennen von Assemblys den Namespace Namen zu befolgen. Eine gute Faustregel besteht darin, die dll basierend auf dem gemeinsamen Präfix der in der Assembly enthaltenen Namespaces zu benennen. Beispielsweise kann eine Assembly mit zwei Namespaces (`MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature``MyCompany.MyTechnology.dll`aufgerufen werden.  
  
 **✓ CONSIDER** naming DLLs nach dem folgenden Muster:  
  
 `<Company>.<Component>.dll`  
  
 , wobei `<Component>` eine oder mehrere durch Punkte getrennte Klauseln enthält. Beispiel:  
  
 `Litware.Controls.dll`.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
