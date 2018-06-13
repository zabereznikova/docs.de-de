---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0110bb42775d8a5df9ca268b35db3abaffec84f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392628"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicherheit und schreibgeschützte öffentliche Arrayfelder
Verwenden Sie niemals schreibgeschützte öffentliche Arrayfelder von verwalteten Bibliotheken bis hin um zu dem Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Arrayfelder geändert werden können.  
  
## <a name="remarks"></a>Hinweise  
 Einige .NET Framework-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Grenze-Parameter enthalten.  Z. B. die <xref:System.IO.Path.InvalidPathChars> Feld ist ein Array, das die Zeichen beschreibt, die nicht in einer Pfadzeichenfolge Datei zulässig sind.  Viele ähnliche Felder, die in der gesamten .NET Framework vorhanden sind.  
  
 Die Werte der öffentliche schreibgeschützte Felder wie <xref:System.IO.Path.InvalidPathChars> kann durch Code oder Code, der Ihr Code die Anwendungsdomäne gemeinsam geändert werden.  Sie sollten nicht schreibgeschützte öffentliche Arrayfelder wie folgt verwenden, um das Verhalten von Anwendungen zu definieren.  Wenn Sie dies tun, kann bösartigem Code die Grenzdefinitionen zu ändern und verwenden Sie Code auf unerwartete Weise.  
  
 In Version 2.0 oder höher von .NET Framework sollten Sie Methoden verwenden, die statt öffentliche Arrayfelder ein neues Array zurückgeben.  Beispielsweise anstelle der <xref:System.IO.Path.InvalidPathChars> Feld, verwenden Sie die <xref:System.IO.Path.GetInvalidPathChars%2A> Methode.  
  
 Beachten Sie, dass .NET Framework-Typen grenztypen intern definieren nicht öffentlichen Felder verwenden.  Stattdessen verwendet das .NET Framework separate private Felder.  Ändern der Werte dieser öffentlichen Felder wird das Verhalten der .NET Framework-Typen nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
