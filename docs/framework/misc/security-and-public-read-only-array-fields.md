---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 2df4acc0606e4fe8fccee4a8acc6ab744dcbbb71
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452707"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicherheit und schreibgeschützte öffentliche Arrayfelder
Verwenden Sie niemals schreibgeschützte öffentliche Array Felder aus verwalteten Bibliotheken, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Array Felder geändert werden können.  
  
## <a name="remarks"></a>Hinweise  

Einige .NET-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungs Parameter enthalten. Beispielsweise ist das <xref:System.IO.Path.InvalidPathChars> Feld ein Array, in dem die Zeichen beschrieben werden, die in einer Dateipfad-Zeichenfolge nicht zulässig sind. In .net sind viele ähnliche Felder vorhanden.  
  
 Die Werte von öffentlichen schreibgeschützten Feldern wie <xref:System.IO.Path.InvalidPathChars> können durch Ihren Code oder Code geändert werden, der die Anwendungsdomäne Ihres Codes freigibt.  Verwenden Sie keine schreibgeschützten öffentlichen Array Felder wie diese, um das Begrenzungs Verhalten Ihrer Anwendungen zu definieren.  Wenn Sie dies tun, kann bösartiger Code die Begrenzungs Definitionen ändern und Ihren Code auf unerwartete Weise verwenden.  
  
 In Version 2,0 und höher der .NET Framework sollten Sie Methoden verwenden, die ein neues Array zurückgeben, anstatt öffentliche Array Felder zu verwenden.  Anstatt das <xref:System.IO.Path.InvalidPathChars>-Feld zu verwenden, sollten Sie z. b. die <xref:System.IO.Path.GetInvalidPathChars%2A>-Methode verwenden.  
  
 Beachten Sie, dass die .NET Framework Typen die öffentlichen Felder nicht zum internen definieren von Begrenzungs Typen verwenden.  Stattdessen verwendet der .NET Framework separate private Felder.  Wenn Sie die Werte dieser öffentlichen Felder ändern, ändert sich das Verhalten von .NET Framework Typen nicht.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
