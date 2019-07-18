---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19b5ad73150697c1442056642a1b11d504ecc426
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61869745"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicherheit und schreibgeschützte öffentliche Arrayfelder
Verwenden Sie niemals schreibgeschützte öffentliche Arrayfelder aus verwalteten Bibliotheken, die Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Arrayfelder geändert werden können.  
  
## <a name="remarks"></a>Hinweise  
 Einige .NET Framework-Klassen sind schreibgeschützte öffentliche Felder, die plattformspezifische Grenzen-Parameter enthalten.  Z. B. die <xref:System.IO.Path.InvalidPathChars> Feld ist ein Array, das die Zeichen beschreibt, die nicht in einer Pfadzeichenfolge Datei zulässig sind.  Viele ähnliche Felder, die in .NET Framework vorhanden sind.  
  
 Die Werte der öffentliche schreibgeschützte Felder wie <xref:System.IO.Path.InvalidPathChars> kann geändert werden, von Ihrem Code oder Code, der in derselben Anwendungsdomäne Ihres Codes verwendet.  Sie sollten nicht schreibgeschützte öffentliche Arrayfelder wie folgt verwenden, um das Verhalten Ihrer Anwendungen zu definieren.  Wenn Sie dies tun, kann schädlichen Code die Grenzdefinitionen alter und verwenden Ihren Code auf unerwartete Weise.  
  
 In Version 2.0 oder höher von .NET Framework sollten Sie Methoden verwenden, die ein neues Array, statt öffentliche Arrayfelder zurückgeben.  Z. B. statt der <xref:System.IO.Path.InvalidPathChars> Feld, verwenden Sie die <xref:System.IO.Path.GetInvalidPathChars%2A> Methode.  
  
 Beachten Sie, die .NET Framework-Typen nicht öffentlichen Felder verwenden, um grenztypen intern zu definieren.  Stattdessen verwendet das .NET Framework separate private Felder.  Ändern Sie die Werte dieser öffentlichen Felder wird das Verhalten der .NET Framework-Typen nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
