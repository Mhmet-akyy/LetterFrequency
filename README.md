# LetterFrequency
import java.util.Map;
import java.util.Scanner;
import java.util.TreeMap;

public class LetterFrequency {
    public static void main(String[] args) {
        
        // 1. Kullanıcıdan kelimeyi al
        Scanner scanner = new Scanner(System.in);
        System.out.print("Kelimeyi giriniz: ");
        String input = scanner.nextLine();
        scanner.close();

        // 2. Büyük/küçük harf farkını kaldır
        input = input.toLowerCase();

        // 3. Harfleri ve frekanslarını saklamak için TreeMap kullanıyoruz
        // TreeMap alfabetik sıralama yapar
        Map<Character, Integer> frequencyMap = new TreeMap<>();

        // 4. Her karakteri kontrol et
        for (char c : input.toCharArray()) {
            if (Character.isLetter(c)) { // sadece harfleri say
                frequencyMap.put(c, frequencyMap.getOrDefault(c, 0) + 1);
            }
        }

        // 5. Sonuçları ekrana yazdır
        System.out.println("\nHarf Frekansları:");
        for (Map.Entry<Character, Integer> entry : frequencyMap.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
