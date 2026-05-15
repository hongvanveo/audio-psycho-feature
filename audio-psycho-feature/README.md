# audio-psycho-feature

Labtainer lab ve giau tin trong am thanh dua vao dac trung quan trong nhat va psychoacoustics.

Co che:

- Am thanh duoc chia thanh cac doan `Si` cung kich thuoc.
- Bit 1 duoc nhung bang cong thuc `S'i(n) = 0.99 * Si(n)`.
- Bit 0 duoc nhung bang cong thuc `S'i(n) = 0.98 * Si(n) + Si(n-d)`.
- Khi tach tin, chuong trinh so sanh do sai khac cua tung doan stego voi hai mo hinh tren.
- Mo hinh nao co sai so nho hon se quyet dinh bit duoc trich xuat.

Lenh mau trong container `sender`:

```bash
cd ~/stego
python3 generate_cover.py --out cover.wav
python3 psycho_feature_stego.py embed --in cover.wav --out stego.wav --message samples/message.txt
python3 psycho_feature_stego.py extract --cover cover.wav --stego stego.wav --out recovered.txt
python3 analyze_audio.py --cover cover.wav --stego stego.wav
```

Luu y: day la dang tach tin can cover goc de so sanh mo hinh, nen `cover.wav` va `stego.wav` deu nen duoc chuyen sang receiver neu thuc hanh tach tin o receiver.

Checkwork co 4 muc trong `instr_config/results.config`.

