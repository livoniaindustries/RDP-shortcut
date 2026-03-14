# ⚡ shortcut for rdp connection

A minimal, no‑fluff guide – only the lines you actually need to touch.  
Open your `.rdp` file in any text editor and replace the values below.

---

## ✏️ what to change – at a glance

| original line (find this) | what to write instead | quick explanation |
|---------------------------|----------------------|--------------------|
| `full address:s:127.0.0.1` | `full address:s:`**`192.168.1.100`** | put the remote computer's IP or hostname |
| `username:s:Administrator` | `username:s:`**`YourName`** | your actual username (local or domain) |
| `password:s:your_password` | `password:s:`**`RealPassword`** | 🔑 **keep this line** – type your real password |
| `desktopwidth:i:1920`<br>`desktopheight:i:1080` | `desktopwidth:i:`**`2560`**<br>`desktopheight:i:`**`1440`** | set your screen resolution (width & height) |
| `screen mode id:i:2` | `screen mode id:i:`**`1`** (window) / **`2`** (full screen) | `2` = full screen (default), `1` = windowed |
| `drivestoredirect:s:*` | `drivestoredirect:s:`**`C:\;D:\`** or keep **`*`** | `*` = all drives, or list specific ones |

> ✅ **all other lines** (`use multimon`, `session bpp`, `winposstr`…) can stay exactly as they are – they work fine with default values.

---

## 🔐 password line – important (but you want it)

the line  
`password:s:your_password`  
**should be kept** – just replace `your_password` with your real password.  

example:  
`password:s:MySecret123`  

> ⚠️ Windows stores this with reversible encryption. anyone with access to the file can decode it.  
> but if you need auto‑login, keep it. otherwise you’d be prompted every time.

---

## 📋 complete edited example (what your file will look like)

```rdp
screen mode id:i:2
use multimon:i:0
desktopwidth:i:1920
desktopheight:i:1080
session bpp:i:32
winposstr:s:0,3,0,0,800,600
full address:s:192.168.1.150      👈 changed IP
username:s:michael                 👈 changed user
password:s:MyRealPassword          👈 changed password (kept)
drivestoredirect:s:*               👈 * means all drives
only these 4–5 lines are edited – everything else untouched.

🚀 shortcut – copy & replace template
copy the block below, paste into a new file, save as something.rdp,
then replace the placeholders YOUR... with your real data.

rdp
screen mode id:i:2
use multimon:i:0
desktopwidth:i:1920
desktopheight:i:1080
session bpp:i:32
winposstr:s:0,3,0,0,800,600
full address:s:YOUR.TARGET.IP
username:s:YOUR-USERNAME
password:s:YOUR-PLAIN-PASSWORD
drivestoredirect:s:*
