# audio-psycho-feature

Labtainer lab ve giau tin trong am thanh dua vao dac trung quan trong nhat va psychoacoustics.

Co che:

- Am thanh duoc chia thanh cac doan `Si` cung kich thuoc.
- Bit 1 duoc nhung bang cong thuc `S'i(n) = 0.99 * Si(n)`.
- Bit 0 duoc nhung bang cong thuc `S'i(n) = 0.98 * Si(n) + Si(n-d)`.
- Khi tach tin, chuong trinh so sanh do sai khac cua tung doan stego voi hai mo hinh tren.
- Mo hinh nao co sai so nho hon se quyet dinh bit duoc trich xuat.

Muc tieu cua lab nay la tao `cover.wav`, nhung thong diep vao `stego.wav`, va danh gia su thay doi giua hai file am thanh. Ham `extract` van duoc giu trong code de dung lai cho lab sau, nhung khong nam trong quy trinh thuc hanh va khong duoc checkwork su dung.

Lenh mau trong container `sender`:

```bash
cd ~/stego
python3 generate_cover.py --out cover.wav
python3 psycho_feature_stego.py embed --in cover.wav --out stego.wav --message samples/message.txt
python3 analyze_audio.py --cover cover.wav --stego stego.wav
cmp cover.wav stego.wav
```

Checkwork co 3 muc trong `instr_config/results.config`:

- `cover_created`
- `stego_created`
- `audio_modified`
