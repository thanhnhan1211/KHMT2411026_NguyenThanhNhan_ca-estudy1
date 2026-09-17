# KHMT2411026_NguyenThanhNhan_ca-estudy1
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      debugShowCheckedModeBanner: false,
      home: ExpenseWelcomeScreen(),
    );
  }
}

class ExpenseWelcomeScreen extends StatelessWidget {
  const ExpenseWelcomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      body: SafeArea(
        child: Padding(
          padding: const EdgeInsets.symmetric(horizontal: 24.0, vertical: 20.0),
          child: Column(
            children: [
              const Spacer(flex: 3),
              
              // Custom Illustration (Ví tiền & tiền)
              const WalletIllustration(),

              const SizedBox(height: 40),

              // Title
              const Text(
                'Expense Manager',
                style: TextStyle(
                  fontSize: 28,
                  fontWeight: FontWeight.bold,
                  color: Color(0xFF102A43),
                  letterSpacing: 0.3,
                ),
              ),

              const SizedBox(height: 16),

              // Subtitle
              const Text(
                'Quản lý chi tiêu cá nhân\nđơn giản và hiệu quả',
                textAlign: TextAlign.center,
                style: TextStyle(
                  fontSize: 16,
                  color: Color(0xFF829AB1),
                  height: 1.4,
                  fontWeight: FontWeight.w400,
                ),
              ),

              const Spacer(flex: 4),

              // Action Button
              SizedBox(
                width: double.infinity,
                height: 54,
                child: ElevatedButton(
                  onPressed: () {},
                  style: ElevatedButton.styleFrom(
                    backgroundColor: const Color(0xFF1976D2),
                    elevation: 0,
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(14),
                    ),
                  ),
                  child: const Text(
                    'Bắt đầu',
                    style: TextStyle(
                      fontSize: 18,
                      fontWeight: FontWeight.w600,
                      color: Colors.white,
                    ),
                  ),
                ),
              ),
              const SizedBox(height: 10),
            ],
          ),
        ),
      ),
    );
  }
}

// Widget vẽ hình minh họa Ví tiền
class WalletIllustration extends StatelessWidget {
  const WalletIllustration({super.key});

  @override
  Widget build(BuildContext context) {
    return SizedBox(
      width: 160,
      height: 140,
      child: Stack(
        alignment: Alignment.bottomCenter,
        children: [
          // Tờ tiền xanh lá phía sau
          Positioned(
            top: 10,
            child: Container(
              width: 110,
              height: 70,
              decoration: BoxDecoration(
                color: const Color(0xFF66BB6A),
                borderRadius: BorderRadius.circular(10),
              ),
            ),
          ),
          // Chiếc ví xanh dương phía trước
          Container(
            width: 160,
            height: 100,
            decoration: BoxDecoration(
              color: const Color(0xFF1976D2),
              borderRadius: BorderRadius.circular(20),
            ),
            child: Stack(
              children: [
                // Khóa nút bấm trên ví
                Positioned(
                  right: 16,
                  top: 25,
                  child: Container(
                    width: 50,
                    height: 38,
                    decoration: BoxDecoration(
                      color: const Color(0xFF1565C0),
                      borderRadius: BorderRadius.circular(8),
                    ),
                    alignment: Alignment.center,
                    child: Container(
                      width: 14,
                      height: 14,
                      decoration: const BoxDecoration(
                        color: Colors.white,
                        shape: BoxShape.circle,
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}
