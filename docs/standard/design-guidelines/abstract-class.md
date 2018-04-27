---
title: Entwurf abstrakter Klassen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a98c40ccc8005789a3a991bfc93deb11786b8943
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="abstract-class-design"></a>Entwurf abstrakter Klassen
**X nicht** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.  
  
 Konstruktoren sollten öffentlich nur, wenn Benutzer zum Erstellen von Instanzen des Typs müssen sein. Da Sie die Instanzen eines abstrakten Datentyps erstellen können, ist ein abstrakter Typ mit einem öffentlichen Konstruktor falsch irreführend, für die Benutzer.  
  
 **Führen Sie ✓** einer geschützten oder internen-Konstruktor in abstrakten Klassen definieren.  
  
 Ein geschützter Konstruktor ist eher üblich und einfach die Basisklasse, um eine eigene Initialisierungsschritte auszuführen. wenn Untertypen erstellt werden kann.  
  
 Ein interner Konstruktor kann verwendet werden, beschränken Sie konkrete Implementierungen von der abstrakten Klasse auf die Assembly, die die Klasse definiert.  
  
 **Führen Sie ✓** Geben Sie mindestens einen konkreten Typ, die von jeder abstrakten Klasse erbt, die Sie versenden.  
  
 Dies So überprüfen Sie den Entwurf einer abstrakten Klasse. Beispielsweise <xref:System.IO.FileStream?displayProperty=nameWithType> ist eine Implementierung der <xref:System.IO.Stream?displayProperty=nameWithType> abstrakte Klasse.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
