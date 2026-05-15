# audio-psycho-feature

Lab nay yeu cau sinh vien thuc hien nhung tin vao audio dua tren dac trung quan trong nhat sau khi tu tao thong diep va sua mot doan code Python mau.

Co che:

- Am thanh duoc chia thanh cac doan `Si` cung kich thuoc.
- Bit 1 duoc nhung bang cong thuc `S'i(n) = 0.99 * Si(n)`.
- Bit 0 duoc nhung bang cong thuc `S'i(n) = 0.98 * Si(n) + Si(n-d)`.
- Qua trinh nhung tao ra file `stego.wav` co sai khac co kiem soat so voi file goc.

Cau truc lab:

- Lab chi dung 1 container duy nhat ten `audio-psycho-feature`.
- Sinh vien thao tac trong thu muc `~/stego`.
- File `embed_task.py` la file can sua de dien ten file audio va ten file thong diep.

Luong thuc hanh:

```bash
cd ~/stego
python3 generate_cover.py --out cover.wav
nano message.txt
nano embed_task.py
python3 embed_task.py
python3 analyze_audio.py --cover cover.wav --stego stego.wav
cmp cover.wav stego.wav
```

Checkwork co 3 muc:

- `cover_created`
- `stego_created`
- `audio_modified`
