---
ms.openlocfilehash: c090e99cd0569a843a4c505ad11b8da5740213e8
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440478"
---
### <a name="blazor-updated-validation-logic-for-static-web-assets"></a>Blazor: Aktualisierte Validierungslogik für statische Webressourcen

Bei der Konfliktvalidierung für statische Webressourcen in ASP.NET Core 3.1 und Blazor WebAssembly 3.2 ist ein Problem aufgetreten. Das Problem:

* hat eine ordnungsgemäße Konflikterkennung zwischen den Hostressourcen und den Ressourcen von Razor-Klassenbibliotheken (Razor Class Library, RCL) und Blazor WebAssembly-Apps verhindert
* hatte in erster Linie Auswirkungen für Blazor WebAssembly-Apps, da statische Webressourcen in RCL standardmäßig unter dem Präfix `_content/$(PackageId)` bereitgestellt werden

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="old-behavior"></a>Altes Verhalten

Bei der Entwicklung konnten die statischen Webressourcen einer RCL ohne Warnung mit den Ressourcen des Hostprojekts auf demselben Hostpfad überschrieben werden. Gehen Sie von einer RCL aus, die eine statische Webressource definiert hat, die unter */folder/file.txt* bereitgestellt wird. Wenn der Host eine Datei in *wwwroot/folder/file.txt* platzierte, überschrieb die Datei auf dem Server ohne Warnung die Datei in der RCL oder in der Blazor WebAssembly-App.

#### <a name="new-behavior"></a>Neues Verhalten

ASP.NET Core erkennt dieses Problem und informiert den Benutzer über den Konflikt, damit er entsprechend reagieren kann.

#### <a name="reason-for-change"></a>Grund für die Änderung

Statische Webressourcen sollten nicht durch Dateien auf dem Host *wwwroot* des Projekts überschrieben werden können. Das Überschreiben dieser Dateien kann zu Fehlern führen, die schwierig zu diagnostizieren sind. Dadurch können nicht definierte Behavior Changes in veröffentlichten Apps auftreten.

#### <a name="recommended-action"></a>Empfohlene Aktion

Standardmäßig gibt es keinen Grund für einen Konflikt zwischen einer RCL-Datei und einer Datei auf dem Host. RCL-Dateien haben das Präfix `_content/${PackageId}`. Blazor WebAssembly-Dateien werden im Stammverzeichnis der Host-URL gespeichert. Dadurch können schneller Konflikte entstehen. Blazor Webassembly-Apps enthalten beispielsweise eine *favicon.ico*-Datei, die der Host möglicherweise auch in seinem *wwwroot*-Stammordner platziert.

Wenn die Konfliktquelle eine RCL-Datei ist, bedeutet dies häufig, dass Code Ressourcen aus der Bibliothek in den Ordner *wwwroot* des Projekts kopiert. Das Schreiben von Code zum Kopieren von Dateien widerspricht einem der Hauptziele von statischen Webressourcen. Dieses Ziel muss erfüllt sein, damit Sie Updates für den Browser erhalten, wenn die Inhalte aktualisiert werden, ohne eine neue Kompilierung auslösen zu müssen.

Sie können dieses Verhalten beibehalten und die Datei auf dem Host verwalten. Entfernen Sie hierzu die Datei aus der Liste der statischen Webressourcen mithilfe eines benutzerdefinierten MSBuild-Ziels.

Wenn Sie die RCL-Datei oder die Datei der Blazor WebAssembly-App anstelle der Datei des Hostprojekts verwenden möchten, entfernen Sie die Datei aus dem Hostprojekt.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
