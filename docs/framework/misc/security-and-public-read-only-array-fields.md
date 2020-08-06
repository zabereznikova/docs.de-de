---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
description: Lesen Sie, warum Sie die Verwendung öffentlicher Schreib geschützter Array Felder vermeiden sollten, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 5e499f8052306cd1ad063c9f44a2a0f1d0b365ef
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855737"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicherheit und schreibgeschützte öffentliche Arrayfelder

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Verwenden Sie niemals schreibgeschützte öffentliche Array Felder aus verwalteten Bibliotheken, um das Begrenzungs Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Array Felder geändert werden können.  
  
## <a name="remarks"></a>Bemerkungen  

Einige .NET-Klassen umfassen schreibgeschützte öffentliche Felder, die plattformspezifische Begrenzungs Parameter enthalten. Das- <xref:System.IO.Path.InvalidPathChars> Feld ist beispielsweise ein Array, in dem die Zeichen beschrieben werden, die in einer Dateipfad-Zeichenfolge nicht zulässig sind. In .net sind viele ähnliche Felder vorhanden.  
  
 Die Werte von öffentlichen schreibgeschützten Feldern wie <xref:System.IO.Path.InvalidPathChars> können durch Ihren Code oder Code geändert werden, der die Anwendungsdomäne Ihres Codes freigibt.  Verwenden Sie keine schreibgeschützten öffentlichen Array Felder wie diese, um das Begrenzungs Verhalten Ihrer Anwendungen zu definieren.  Wenn Sie dies tun, kann bösartiger Code die Begrenzungs Definitionen ändern und Ihren Code auf unerwartete Weise verwenden.  
  
 In Version 2,0 und höher der .NET Framework sollten Sie Methoden verwenden, die ein neues Array zurückgeben, anstatt öffentliche Array Felder zu verwenden.  Anstatt das-Feld zu verwenden <xref:System.IO.Path.InvalidPathChars> , sollten Sie z. b. die- <xref:System.IO.Path.GetInvalidPathChars%2A> Methode verwenden.  
  
 Beachten Sie, dass die .NET Framework Typen die öffentlichen Felder nicht zum internen definieren von Begrenzungs Typen verwenden.  Stattdessen verwendet der .NET Framework separate private Felder.  Wenn Sie die Werte dieser öffentlichen Felder ändern, ändert sich das Verhalten von .NET Framework Typen nicht.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
