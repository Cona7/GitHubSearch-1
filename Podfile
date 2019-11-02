source 'https://cdn.cocoapods.org/'
# Uncomment the next line to define a global platform for your project
platform :ios, '11.0'

target 'GitHubSearch' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!
  inhibit_all_warnings!

  # Pods for GitHubSearch

  # Networking
  pod 'Moya'                                # https://github.com/Moya/Moya
  pod 'AlamofireNetworkActivityIndicator'   # https://github.com/Alamofire/AlamofireNetworkActivityIndicator

  # Persistance
  pod 'RealmSwift'  # https://github.com/realm/realm-cocoa

  # Image
  pod 'Kingfisher'  # https://github.com/onevcat/Kingfisher

  # UI
  pod 'Localize-Swift'  # https://github.com/marmelroy/Localize-Swift

  # Tools
  pod 'R.swift'       # https://github.com/mac-cain13/R.swift
  pod 'SwifterSwift'  # https://github.com/SwifterSwift/SwifterSwift

  # Keychain
  pod 'KeychainAccess'  # https://github.com/kishikawakatsumi/KeychainAccess

  # Color
  pod 'ChameleonFramework/Swift', :git => 'https://github.com/ViccAlexander/Chameleon.git'

  # Auto Layout
  pod 'SnapKit'    # https://github.com/SnapKit/SnapKit

  # Code Quality
  pod 'SwiftLint'   # https://github.com/realm/SwiftLint

end

# Cocoapods optimization, always clean project after pod updating
post_install do |installer|
  Dir.glob(installer.sandbox.target_support_files_root + "Pods-*/*.sh").each do |script|
      flag_name = File.basename(script, ".sh") + "-Installation-Flag"
      folder = "${TARGET_BUILD_DIR}/${UNLOCALIZED_RESOURCES_FOLDER_PATH}"
      file = File.join(folder, flag_name)
      content = File.read(script)
      content.gsub!(/set -e/, "set -e\nKG_FILE=\"#{file}\"\nif [ -f \"$KG_FILE\" ]; then exit 0; fi\nmkdir -p \"#{folder}\"\ntouch \"$KG_FILE\"")
      File.write(script, content)
  end
end
