---
ms.openlocfilehash: 3d8179c5c0e84f8ff1197cce7790c80a5f5a4f6d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619447"
---

Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert. Wenn Sie jedoch .NET Core manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:

- krb5-libs
- libicu
- openssl-libs

Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- [libgdiplus (Version 6.0.1 oder höher)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen. Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.
