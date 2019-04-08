---
ms.openlocfilehash: 97ca78e154eb25e863256e06caa119fe753bc344
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761287"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="90f56-101">Die Rechtschreibüberprüfung in textfähigen WPF-Steuerelementen funktioniert unter Windows 10 nicht für die Sprachen, die nicht in der Liste der Eingabesprachen in dem Betriebssystem aufgeführt sind</span><span class="sxs-lookup"><span data-stu-id="90f56-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

|   |   |
|---|---|
|<span data-ttu-id="90f56-102">Details</span><span class="sxs-lookup"><span data-stu-id="90f56-102">Details</span></span>|<span data-ttu-id="90f56-103">Bei einem Windows 10-Betriebssystem kann es sein, dass die Rechtschreibüberprüfung für textfähige WPF-Steuerelemente nicht funktioniert, da die plattformspezifischen Funktionen zur Rechtsschreibüberprüfung nur für die Sprachen verfügbar sind, die in der Liste mit den Eingabesprachen aufgeführt sind. Wenn in Windows 10 eine Sprache zu der Liste mit verfügbaren Tastaturen hinzugefügt wird, lädt Windows automatisch ein passendes Feature-On-Demand-Paket herunter, das Funktion zur Rechtschreibüberprüfung enthält, und installiert dieses.</span><span class="sxs-lookup"><span data-stu-id="90f56-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="90f56-104">Durch das Hinzufügen der Sprache zur Eingabesprachenliste wird die Rechtschreibprüfung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90f56-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>|
|<span data-ttu-id="90f56-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="90f56-105">Suggestion</span></span>|<span data-ttu-id="90f56-106">Beachten Sie, das die Sprache oder der Text, deren bzw. dessen Rechtschreibung überprüft werden muss, als Eingabesprache hinzugefügt werden muss, damit die Rechtschreibüberprüfung in Windows 10 funktioniert.</span><span class="sxs-lookup"><span data-stu-id="90f56-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>|
|<span data-ttu-id="90f56-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="90f56-107">Scope</span></span>|<span data-ttu-id="90f56-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="90f56-108">Edge</span></span>|
|<span data-ttu-id="90f56-109">Version</span><span class="sxs-lookup"><span data-stu-id="90f56-109">Version</span></span>|<span data-ttu-id="90f56-110">4.6</span><span class="sxs-lookup"><span data-stu-id="90f56-110">4.6</span></span>|
|<span data-ttu-id="90f56-111">Typ</span><span class="sxs-lookup"><span data-stu-id="90f56-111">Type</span></span>|<span data-ttu-id="90f56-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="90f56-112">Runtime</span></span>|

