---
title: Namen von Assemblys und DLLs
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570424"
---
# <a name="names-of-assemblies-and-dlls"></a>Namen von Assemblys und DLLs
Eine Assembly ist die Einheit der Bereitstellung und Identität für verwalteten Code Programme. Obwohl Assemblys eine oder mehrere Dateien umfassen können, in der Regel ordnet eine Assembly eine DLL eins zu eins. Dieser Abschnitt beschreibt daher nur DLL Benennungskonventionen, der dann Benennungskonventionen Assembly zugeordnet werden können.  
  
 **Führen Sie ✓** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.  
  
 Assembly- und DLL-Namen müssen den Namespace-Namen entsprechen, aber es ist angemessen, des Namespacenamens befolgen beim Benennen von Assemblys. Eine gute Faustregel ist, der basierend auf einem gemeinsamen Präfix der Namespaces in der Assembly enthaltenen DLL-name. Angenommen, eine Assembly mit zwei Namespaces `MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature`, aufgerufen werden `MyCompany.MyTechnology.dll`.  
  
 **✓ GGF.** naming DLLs nach dem folgenden Muster:  
  
 `<Company>.<Component>.dll`  
  
 wobei `<Component>` enthält eine oder mehrere Punkte getrennte Klauseln. Zum Beispiel:  
  
 `Litware.Controls.dll`  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
