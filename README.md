```swift 
//
//  RatingsView.swift
//  SleepWave
//
//  Created by paige on 2022/02/03.
//
import SwiftUI

struct RatingsView: View {
    
    @Binding var selected: Int
    
    var body: some View {
        HStack(spacing: 10) {
            ForEach(0..<5) { i in
                Image(systemName: "star.fill")
                    .resizable()
                    .frame(width: 30, height: 30)
                    .foregroundColor(self.selected >= i ? RatingColor : InactiveRatingColor)
                    .onTapGesture {
                        self.selected = i
                    }
            } //: FOREACH
        } //: HSTACK
    }
    
}

#if DEBUG
struct RatingsView_Previews: PreviewProvider {
    static var previews: some View {
        RatingsView(selected: .constant(3))
    }
}
#endif 

extension RatingsView {
    
    var RatingColor: Color {
        Color(red: 87/255, green: 81/255, blue: 255/255)
    }
    
    var InactiveRatingColor: Color {
        Color(red: 77/255, green: 77/255, blue: 77/255)
    }
    
}
```swift 
