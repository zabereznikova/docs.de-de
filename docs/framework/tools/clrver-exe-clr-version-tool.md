---
title: Clrver.exe (CLR-Versionstool)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: bfc612ef5455e1b4a03d15fd99a8a1873d2c7c08
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715799"
---
# <a name="clrverexe-clr-version-tool"></a>Clrver.exe (CLR-Versionstool)
Das CLR-Versionstool (Clrver.exe) führt alle installierten Versionen der Common Language Runtime (CLR) auf dem Computer auf.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a>Optionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`-all`|Zeigt alle Prozesse auf dem Computer an, die die CLR verwenden.|  
|*pid*|Zeigt die Versionen der CLR an, die von dem Prozess verwendet werden, der über angegebene Prozess-ID (PID) aufweist.|  
|`-?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie "Clrver.exe" ohne Optionen aufrufen, werden alle installierten CLR-Versionen angezeigt. Wenn Sie eine PID für einen anderen Benutzer angeben, müssen Sie über Administratorberechtigungen verfügen, um die Versionsinformationen abzurufen.  
  
> [!NOTE]
> Unter Windows Vista (und höher) werden die Berechtigungen eines Benutzers von der Benutzerkontensteuerung (User Account Control, UAC) bestimmt. Als Mitglied der integrierten Administratorgruppe sind Ihnen zwei Zugriffstoken für die Laufzeit zugewiesen: ein Standardbenutzertoken und ein Administratorzugriffstoken. Standardmäßig verwenden Sie die Standardbenutzerrolle. Um Code ausführen zu können, der Administratorberechtigungen erfordert, müssen Sie zuerst Ihre Berechtigungen von Standardbenutzer auf Administrator erhöhen. Dazu starten Sie die Eingabeaufforderung, indem Sie mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung klicken und angeben, dass Sie die Anwendung als Administrator ausführen möchten.  
  
 Der Versuch, die CLR-Version für SYSTEM-, LOCAL SERVICE- und NETWORK SERVICE-Prozesse zu bestimmen, führt zu einer Meldung, die besagt, dass die PID nicht vorhanden ist.  
  
## <a name="examples"></a>Beispiele  
 Mit dem folgenden Befehl werden alle Versionen der CLR angezeigt, die auf dem Computer installiert sind.  
  
 `clrver`  
  
 Mit dem folgenden Befehl wird die Version der CLR angezeigt, die von Prozess 128 verwendet wird.  
  
 `clrver 128`  
  
 Der folgende Befehl zeigt alle verwalteten Prozesse und die Version der CLR, die sie verwenden, an.  
  
 `Clrver -all`  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
