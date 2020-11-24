---
title: Namespaces und DTDs im DOM
ms.date: 03/30/2017
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
ms.openlocfilehash: bd2a15b96cb456f475eb7dec439a0f328ae72a55
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830141"
---
# <a name="namespaces-and-dtds-in-the-dom"></a>Namespaces und DTDs im DOM
DTDs (Document Type Definition) erschweren die Namespace-Unterstützung. Das folgende XML-Beispiel enthält Standardattribute, deren Namen Doppelpunkte enthalten.  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 Folgende Auflösungen sind möglich, wenn dieses Konstrukt zulässig ist:  
  
- `x:` wird als Namespacepräfix behandelt, aber dieses Präfix muss mit einer `xmlns:x`-Namespacedeklaration auflösbar sein, die auch an einer beliebigen Stelle in der DTD vorhanden sein muss. Wenn das Präfix einem anderen Element im Instanzdokument zugeordnet wird, stellt dies einen Fehler dar.  
  
- `x:` wird als Namespacepräfix behandelt, aber dieses Präfix wird immer im Kontext der Instanzelemente aufgelöst. Das bedeutet, dass das Präfix im Grunde verschiedenen Namespace-URIs (Uniform Resource Identifier) zugeordnet werden könnte, je nachdem, in welchem Namespacegültigkeitsbereich das `item`-Element auftritt. Dieses Verhalten ist besser vorhersagbar als die im vorherigen Punkt beschriebene Auflösung; es hat jedoch andere komplizierte Auswirkungen, da es die Materialisierung der Standardattribute erfordert.  
  
- Der Doppelpunkt wird ignoriert, da er in einer DTD vorkommt, und der Name des Attributs ist `x:y`. Es ist kein Präfix und kein Namespace-URI vorhanden.  
  
- Der Doppelpunkt im Standardattribut löst eine Ausnahme aus, die besagt, dass Doppelpunkte in Namen innerhalb einer DTD nicht unterstützt werden. Dies führt zu einem vorhersagbaren Verhalten, bedeutet aber auch, dass Sie nur einige der vom W3C (World Wide Web Consortium) veröffentlichten DTDs laden können.  
  
- Wenn der Benutzer eine DTD-Validierung anfordert, wird die Unterstützung von Namespaces für das gesamte Dokument deaktiviert. Dadurch können W3C-DTDs geladen werden, und es ergibt sich ein vorhersagbares Verhalten.  
  
 Beim XML-Code in Microsoft .NET Framework wird die zweite Option implementiert, um maximale Kompatibilität mit der W3C-Spezifikation zu gewährleisten.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
